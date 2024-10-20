## API cheatsheet

### CURL en API
|Command|Description|
|---|---|
|curl http://<SERVER_IP>:<PORT>/api.php/city/london|Read entry|
|curl -s http://<SERVER_IP>:<PORT>/api.php/city/ | jq|Read all entries|
|curl -X POST http://<SERVER_IP>:<PORT>/api.php/city/ -d '{"city_name":"HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json'|	create (add) entry|
|curl -X PUT http://<SERVER_IP>:<PORT>/api.php/city/london -d '{"city_name":"New_HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json'|Update (modify) entry|
|curl -X DELETE http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City|Delete entry|

