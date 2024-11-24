# Home Assistant with Nginx Reverse Proxy and Zigbee2MQTT

This repository is a **cookie-cutter template** for setting up a **Home Assistant** server exposed to the internet via
an **Nginx reverse proxy** with **Zigbee2MQTT** support. All components run in **Docker** containers for easy management
and deployment.

## Prerequisites

- cookiecutter installed
- Docker and Docker Compose installed
- A registered domain name (optional but recommended for SSL)
- A Zigbee USB stick (for Zigbee2MQTT if relevant)

## Setup Instructions

### 1. Clone and Generate Template from Cookie Cutter

First, clone this repository and generate a project from the template:

```bash
cookiecutter gh:karim-ramadan/home-assistant-template
```

Now you are ready to set up your own home assistant instance 
check [Internal readme for more info](%7B%7Bcookiecutter.repo_name%7D%7D/README.md)

