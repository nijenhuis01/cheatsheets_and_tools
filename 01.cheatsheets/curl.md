## cURL cheatsheet

### cURL options
|Command|Description|
|---|---|
|curl inlanefreight.com|Basic GET request|
|curl -s -O inlanefreight.com/index.html|Download file|
|curl -k https://inlanefreight.com|Skip HTTPS (SSL) certificate validation|
|curl inlanefreight.com -v|Print full HTTP request/response details|
|curl -I https://www.inlanefreight.com|Send HEAD request (only prints response headers)|
|curl -i https://www.inlanefreight.com|Print response headers and response body|
|curl https://www.inlanefreight.com -A 'Mozilla/5.0'|Set User-Agent header|
|curl -u admin:admin http://<SERVER_IP>:<PORT>/|Set HTTP basic authorization credentials|
|curl http://admin:admin@<SERVER_IP>:<PORT>/|Pass HTTP basic authorization credentials in the URL|
|curl -H 'Authorization: Basic YWRtaW46YWRtaW4='|http://<SERVER_IP>:<PORT>/	Set request header|
|curl 'http://<SERVER_IP>:<PORT>/search.php?search=le'|Pass GET parameters|
|curl -X POST -d 'username=admin&password=admin'|http://<SERVER_IP>:<PORT>/	Send POST request with POST data|
|curl -b 'PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1'|http://<SERVER_IP>:<PORT>/	Set request cookies|
|curl -X POST -d '{"search":"london"}' -H 'Content-Type: application/json'|http://<SERVER_IP>:<PORT>/search.php	Send POST request with JSON data|
|curl -IL http://test.nl|Grab webiste banner|
|curl <ip>/robots.txt|List potential directories|
