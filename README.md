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
![Dashboard Demo](energy.gif)

### Floor 1
![Automation Demo](v1.gif)

### Buttons
![Plex Demo](button.gif)

### Floorplan
![Plex Demo](fp.gif)

---
