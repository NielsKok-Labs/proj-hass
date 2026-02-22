# proj-hass
# Self-Hosted Smart Home Platform

This project is a self-hosted Home Assistant environment running on a Raspberry Pi using Docker.  
It includes a Plex media server, containerized services, and remote access via Tailscale VPN.

---

## Features

- Home Assistant for smart home automation
- Plex Media Server in Docker
- Remote access through Tailscale VPN
- Containerized services
- Network segmentation & secure access
- Automated backups and updates

---

## Architecture Overview

Raspberry Pi
│
├─ Docker
│ ├─ home-assistant
│ ├─ plex
│ └─ optional containers (Pi-hole, others)
│
└─ Network
├─ VLAN / segmentation
└─ Remote access via Tailscale VPN

---

## Demo GIFs

### Dashboard
<img src="energy.gif" alt="Dashboard Demo" width="480"/>

### Floor 1
<img src="v1.gif" alt="Automation Demo" width="480"/>

### Buttons
<img src="buttons.gif" alt="Buttons Demo" width="480"/>

### Floorplan
<img src="fp.gif" alt="Floorplan Demo" width="480"/>

---
