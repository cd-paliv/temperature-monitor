# IoT Entrega Final

This project is the final delivery for the IoT course. It includes an IoT system that monitors temperature and controls windows using MQTT, InfluxDB, Node-RED, and Grafana.

## Installation

1. Install Arduino IDE version 1.8.19.
2. Use the Mosquitto MQTT broker at `test.mosquitto.org`.

## Project Structure

- `central/central.ino`: Arduino code for the ESP32 client that connects to WiFi and publishes temperature data to the MQTT broker.
- `docker-compose.yml`: Docker Compose file to set up InfluxDB, Node-RED, and Grafana services.
- `node-red-data/`: Contains Node-RED flow configurations and settings.
- `grafana/`: Contains Grafana provisioning and data directories.
- `mosquitto/config/mosquitto.conf`: Configuration file for the Mosquitto MQTT broker.

## How to Run

1. Clone the repository:
    ```sh
    git clone https://github.com/jurten/iot-entrega-final.git
    cd iot-entrega-final
    ```

2. Start the Docker services:
    ```sh
    docker-compose up -d
    ```

3. Upload the  code to your ESP32 using the Arduino IDE.

## Node-RED Flows

The Node-RED flows are configured to:
- Receive temperature data from the MQTT broker.
- Store the data in InfluxDB.
- Send notifications via Telegram.

## Grafana Dashboard

Grafana is used to visualize the temperature data stored in InfluxDB. The dashboard is pre-configured and can be accessed at `http://localhost:3000` with the default credentials (`admin`/`admin`).
