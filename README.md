# IoT Docker Stack
[![Grafana](https://img.shields.io/badge/Grafana-F46800.svg?style=for-the-badge&logo=Grafana&logoColor=white)]() [![InfluxDB](https://img.shields.io/badge/InfluxDB-22ADF6.svg?style=for-the-badge&logo=InfluxDB&logoColor=white)]() [![Mosquitto](https://img.shields.io/badge/Eclipse%20Mosquitto-3C5280.svg?style=for-the-badge&logo=Eclipse-Mosquitto&logoColor=white)]()
## Instructions
1. Clone this repo
2. Enter in the repo directory
3. modify `.env` file according your preferences
4. Create the directories according to your `.env` file variables

    For the current variables of the `.env` file it should be:
    ```bash
    sudo mkdir /{volume1,volume1/Docker}
    sudo mkdir /volume1/Docker/{influxdb,grafana,mosquitto}
    sudo mkdir /volume1/Docker/grafana/data
    sudo mkdir /volume1/Docker/mosquitto/{config,data,log}
    ```
5. Copy `mosquitto.conf` to `MOSQUITTO_CONFIG` path
    ```bash
    sudo cp mosquitto.conf /volume1/Docker/mosquitto/config
    ```
6. Change the owner directory for `GRAFANA_PATH`
    ```bash
    sudo chown -R 472:472 /volume1/Docker/grafana/data
    ```
7. Enter to `iot-services` directory and run `docker-compose up -d` command
    ```bash
    cd iot-services
    sudo docker-compose up -d
    ``` 
8. Once finished we check the services
    
    For `Grafana` access the address `http://<HOST_IP>:3000`, the default user and password is `admin`.

    For `InfluxDB` access the address `http://<HOST_IP>:8086` and complete the initial configuration. 