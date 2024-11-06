## Services Overview

### 1. DuckDNS

DuckDNS is a free Dynamic DNS (DDNS) service that allows you to assign a domain name to your dynamic IP address. This is
particularly useful if you have a home server and want to access it remotely with a domain name.

- **Purpose**: Provides a static domain name for a dynamic IP.
- **Directory**: [duckdns](duckdns)
- **Configuration**: The service is configured to update the DNS record automatically whenever your home IP address
  changes.

### 2. Nginx Reverse Proxy

Nginx is configured as a reverse proxy to route external HTTP(S) traffic to internal services like Home Assistant. It
handles SSL encryption and ensures secure access to your services over the internet.

- **Purpose**: Exposes Home Assistant and other services to the outside world via a secure, reverse proxy setup.
- **Directory**: [proxy](proxy)
- **Configuration**: The Nginx configuration includes SSL setup using Let's Encrypt for secure HTTPS access.

### 3. Mosquitto MQTT Broker

Mosquitto is a lightweight, open-source MQTT broker. It's used for communication between IoT devices and applications.
This service handles the MQTT protocol, allowing Home Assistant and Zigbee2MQTT to send and receive messages from other
devices.

- **Purpose**: Acts as a message broker for IoT devices.
- **Directory**: [mosquitto](mosquitto)
- **Configuration**: Configured to allow secure MQTT communication with the Home Assistant and Zigbee2MQTT services.

### 4. Home Assistant

Home Assistant is an open-source platform for smart home automation. It runs in its own container and is the central hub
for managing and automating your IoT devices.

- **Purpose**: The main smart home automation platform.
- **Directory**: [home-assistant](home-assistant)
- **Configuration**: Home Assistant is configured to use the MQTT broker and to be accessible remotely via the Nginx
  reverse proxy.

### 5. Zigbee2MQTT

Zigbee2MQTT is an open-source project that allows you to control Zigbee devices (like lights, sensors, and locks) from
Home Assistant via MQTT. It works with various Zigbee coordinators (USB sticks).

- **Purpose**: Allows Zigbee devices to be controlled via MQTT and integrated with Home Assistant.
- **Directory**: [zigbee2mqtt](zigbee2mqtt)
- **Configuration**: The Zigbee2MQTT configuration allows you to specify your Zigbee coordinator device and MQTT broker
  settings.

## How to Use

1. Inside of your DNS provider setup up:

- If you have a static IP address an A record pointing to your static IP
- If you have a public IP but it is not static Set up a CNAME pointing to {{ cookiecutter.duckdns_subdomain }}

1. Run the `dcup` script to start all services:

   ```bash
   ./dcup
   ```

1. Access the Home Assistant UI via `https://<your_domain>`. The other services (like Mosquitto and Zigbee2MQTT) will be
   running in the background, allowing Home Assistant to interact with your IoT devices.

## Useful Commands

- **Start all services**: `./dcup`
- **Stop all services**: `./dcup -d`
- **View logs**: `docker-compose logs -f [service_name]`