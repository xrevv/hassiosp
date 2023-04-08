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
# Warning
Running this project "as is" in a production environment is highly discouraged, because of leaked private keys and passwords visible in config files! This is just for demonstration purposes.
