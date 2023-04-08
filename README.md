<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#warning">Warning</a></li>
    <li><a href="#built-with">Built with</a></li>
    <li><a href="#about-the-project">About The Project</a></li>
    <li><a href="#logins-and-passwords">Logins and passwords</a></li>
    <li><a href="#setup">Setup</a></li>
  </ol>
</details>

<!-- WARNING -->
# Warning
Running this project "as is" in a production environment is highly discouraged, because of leaked private keys and passwords visible in config files! This is just for demonstration purposes.

<!-- BUILT WITH -->
# Built with
[![docker][docker]][docker-url]
[![homeassistant][homeassistant]][homeassistant-url]
[![portainer][portainer]][portainer-url]
[![influxdb][influxdb]][influxdb-url]
[![grafana][grafana]][grafana-url] 

[![labview][labview]][labview-url] 

<!-- ABOUT THE PROJECT -->
# About The Project
The aim of the project is to create an unofficial LabVIEW integration in Home Assistant. The data is gathered in LabVIEW and sent to InfluxDB. Visualization is done in Grafana. Everything under Home Assistant.

<!-- LOGINS AND PASSWORDS -->
# Logins and passwords
Login to everything:
```
hassiosp
```
Password to everything (except Portainer):
```
hassiosp
```
Password to Portainer:
```
hassiosphassiosp
```

<!-- SETUP -->
# Setup
### Run this script after cloning to set correct permissions
```
cd hassio/
./configure 
```
### Running the containers
```
cd hassio/
./set_ip
docker-compose up -d 
```
### Stopping the containers
```
cd hassio/
docker-compose down 
./rev_ip
```
## Warning
set_ip and rev_ip require ifconfig

<!-- MARKDOWN LINKS & IMAGES -->
[docker]: https://img.shields.io/badge/docker-2496ED?style=for-the-badge&logo=docker&logoColor=FFFFFF
[docker-url]: https://www.docker.com/
[homeassistant]: https://img.shields.io/badge/homeassistant-41BDF5?style=for-the-badge&logo=homeassistant&logoColor=FFFFFF
[homeassistant-url]: https://www.home-assistant.io/
[portainer]: https://img.shields.io/badge/portainer-13BEF9?style=for-the-badge&logo=portainer&logoColor=FFFFFF
[portainer-url]: https://www.portainer.io/
[influxdb]: https://img.shields.io/badge/influxdb-22ADF6?style=for-the-badge&logo=influxdb&logoColor=FFFFFF
[influxdb-url]: https://www.influxdata.com/
[grafana]: https://img.shields.io/badge/grafana-F46800?style=for-the-badge&logo=grafana&logoColor=FFFFFF
[grafana-url]: https://grafana.com/
[labview]: https://img.shields.io/badge/labview-FFDB00?style=for-the-badge&logo=labview&logoColor=000000
[labview-url]: https://www.ni.com/pl-pl/shop/labview.html
