# proj-hass
# Self-Hosted Smart Home Automation Platform

This repository documents the architecture and implementation of my self-hosted smart home platform.

The environment runs on a Raspberry Pi using Docker and is designed around modularity, isolation, and energy-aware decision making.  
It combines automation, media services, workflow orchestration, and secure remote access into a cohesive system.

This is not a distributable project, but a documentation of architectural choices and automation strategy.

---

## Architectural Goals

- Full self-hosted control (no cloud dependency required)
- Service isolation through containerization
- Zero public exposure of internal services
- Energy-aware automation logic
- Clear separation between stable production automations and experimental workflows
- Maintainable and extensible design

---

## System Architecture

The platform runs entirely on a Raspberry Pi with Docker as the orchestration layer.

### Core Services

- **Home Assistant** – Primary automation and orchestration layer  
- **Music Assistant** – Multi-room audio abstraction layer (Sonos integration)  
- **Plex Media Server** – Containerized local media streaming  
- **n8n (PoC environment)** – Workflow automation experimentation  
- **Tailscale VPN** – Secure remote connectivity  

### Design Decisions

**Containerization**
- Each service runs in its own container
- Clear separation of concerns
- Independent lifecycle management
- Simplified upgrades and rollback capability

**Security Model**
- No inbound ports exposed to the internet
- Encrypted device-to-device connectivity via Tailscale
- Network segmentation within the local environment
- Secrets isolated from configuration

**Automation Layering**
- Home Assistant handles deterministic, production-grade automations
- n8n is used for experimental logic and external integrations
- This prevents instability in core smart home operations

---

## Energy-Aware Automation Strategy

A key focus of this platform is adaptive energy usage.

The system continuously monitors energy input and adjusts high-consumption devices accordingly.

Examples:

- Climate systems activate when surplus energy is available
- Load is reduced during low production periods
- Consumption spikes are minimized through conditional triggers

The goal is not simple automation, but responsive system behavior based on environmental input.

---

## Multi-Room Audio Abstraction

Music Assistant is used to decouple automation logic from vendor-specific ecosystems.

Capabilities include:

- Unified control of multiple speakers
- Sonos integration
- Synchronized multi-room playback
- Automation-triggered announcements
- Context-aware audio behavior

By abstracting the audio layer, speaker brand becomes an implementation detail rather than a system constraint.

---

## Media & Service Integration

Plex Media Server runs as an isolated container and integrates into the broader self-hosted ecosystem.

This maintains service independence while preserving network-level control and segmentation.

---

## Demo

### Core Views

<table>
  <tr>
    <td align="center">
      <img src="energy.gif" alt="Energy Dashboard Demo" width="300"/>
      <p><strong>Energy Dashboard</strong></p>
    </td>
    <td align="center">
      <img src="v1.gif" alt="Floor 1 Demo" width="300"/>
      <p><strong>Floor 1 Overview</strong></p>
    </td>
    <td align="center">
      <img src="buttons.gif" alt="Automation Controls Demo" width="300"/>
      <p><strong>Automation Controls</strong></p>
    </td>
  </tr>
</table>

<div align="center" style="margin-top:20px;">
  <img src="flpl.gif" alt="Interactive Floorplan Demo" width="900"/>
  <p><strong>Interactive Floorplan</strong></p>
</div>

---

## Event-Driven UI Adaptation

The dashboard automatically transitions to an evening theme based on sunset events.

This is implemented using Home Assistant’s sun entity and demonstrates:

- Event-driven state transitions  
- UI adaptation based on environmental context  
- Clean separation between logic and presentation  

▶️ [Watch the demo video](hass.mp4)

---

## What This Project Demonstrates

- Practical container orchestration on constrained hardware  
- Secure remote-first architecture without reverse proxies  
- Energy-optimized automation design  
- Layered automation strategy  
- Vendor abstraction for long-term flexibility  
- Real-world infrastructure decision making  

---

This repository serves as architectural documentation of a secure, modular, and energy-aware smart home platform.
