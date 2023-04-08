## Run this script after cloning to set correct permissions
```
cd hassio/
./configure 
```
## Running the containers
```
cd hassio/
./set_ip
docker compose up -d 
```
## Stopping the containers
```
cd hassio/
docker compose down 
./rev_ip
```
## Warning
set_ip and rev_ip requires ifconfig
