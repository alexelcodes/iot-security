# IoT Security

<p align="center">
  <img src="https://img.shields.io/badge/Platform-ESP32-blue"/>
  <img src="https://img.shields.io/badge/Framework-ESP--IDF-orange"/>
  <img src="https://img.shields.io/badge/Platform-Kali%20Linux-black"/>
  <img src="https://img.shields.io/badge/Protocol-MQTT-yellow"/>
  <img src="https://img.shields.io/badge/Security-TLS%20%2F%20X.509-blue"/>
  <img src="https://img.shields.io/badge/Attacks-MITM%20%7C%20Buffer%20Overflow-red"/>
  <img src="https://img.shields.io/badge/Pentesting-Nmap%20%7C%20OpenVAS-lightgrey"/>
  <img src="https://img.shields.io/badge/Containers-Docker-blue"/>
</p>

## Overview

This repository contains practical IoT security projects and configuration files focused on analyzing and testing embedded and networked systems. The work involves real hardware, custom network setups, and common security tools to evaluate both vulnerabilities and defensive techniques.

## Topics Covered

**Foundations**

- Ethical hacking principles and legal boundaries
- Secure network setup for IoT experimentation

**Infrastructure**

- EdgeRouter X configuration and firewall rules
- Raspberry Pi setup as a Wi-Fi access point and Docker host
- Full IoT stack deployment using MQTT, InfluxDB, Node-RED, and Grafana

**Vulnerabilities & Attacks**

- Vulnerability scanning with Kali Linux and OpenVAS
- Attacks on IoT protocols: MITM on MQTT
- Exploiting memory vulnerabilities: buffer overflow on embedded systems

**Defensive Techniques**

- Secure firmware development for ESP32 devices
- Securing MQTT communication with TLS and client authentication

## Projects

1. [Environment Setup](01-environment-setup/)  
   Configure a secure testing environment including EdgeRouter X, Raspberry Pi with a Docker-based IoT stack, and an ESP32 MQTT client.

2. [Network Scanning and Recon](02-network-scanning-and-recon/)  
   Capture ARP and TCP traffic, scan the local network with Nmap, and identify vulnerabilities using OpenVAS and other Kali Linux tools.

3. [MQTT MITM and Packet Modification](03-mqtt-mitm/)  
   Perform a Man-in-the-Middle (MITM) attack on MQTT traffic, analyze message flows, and modify published data using ettercap and bettercap.

4. [Buffer Overflow Attack](04-buffer-overflow-attack/)  
   Exploit a buffer overflow in a vulnerable C program running on ESP32. Craft and inject a payload that overwrites the return address and triggers hidden functionality.

5. [MQTT Hardening](05-mqtt-hardening/)  
   Establish a secure TLS channel for MQTT communication with mutual certificate authentication and validate the connection between ESP32 and Mosquitto using manually generated certificates.

## Requirements

- **Raspberry Pi 4 (64-bit OS)** — hosts the IoT stack (MQTT, Node-RED, InfluxDB, Grafana)
- **ESP32-C6** — used as an embedded target device for security testing and validation
- **EdgeRouter X** — provides network segmentation and firewalling
- **Kali Linux VM** — used as the attacker machine (Nmap, OpenVAS, Bettercap, etc.)
