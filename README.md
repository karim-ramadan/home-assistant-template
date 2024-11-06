# Home Assistant with Nginx Reverse Proxy and Zigbee2MQTT

This repository is a **cookie-cutter template** for setting up a **Home Assistant** server exposed to the internet via an **Nginx reverse proxy** with **Zigbee2MQTT** support. All components run in **Docker** containers for easy management and deployment.

## Prerequisites

- Docker and Docker Compose installed
- A registered domain name (optional but recommended for SSL)
- A Zigbee USB stick (for Zigbee2MQTT if relevant)

## Setup Instructions

### 1. Clone and Generate Template from Cookie Cutter

First, clone this repository and generate a project from the template:

```bash
git clone https://github.com/karim-ramadan/home-assistant-template
cd home-assistant-template
cookiecutter .
