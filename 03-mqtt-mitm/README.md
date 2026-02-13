# MQTT MITM and Packet Modification

## Overview

This project demonstrates a **Man-in-the-Middle (MITM) attack** on MQTT traffic within a LAN and shows how MQTT packets can be intercepted and modified in transit.

It focuses on practical network-level traffic manipulation in IoT systems using tools such as **Ettercap** and **Bettercap**.

## Key Features:

- Captures and analyzes normal MQTT traffic flow using tcpdump
- Performs MITM attack using ARP poisoning to discover MQTT clients
- Visualizes traffic flow with and without MITM using sequence diagrams
- Modifies live MQTT packet payloads using Bettercap and a custom JavaScript filter
- Built on a real IoT setup with Raspberry Pi, ESP32, Mosquitto broker, and Kali VM

## Project Files

The project includes:

- `normal-mqtt-flow.md`: Sequence diagram of the normal MQTT message path
- `mitm-mqtt-flow.md`: Modified diagram showing MITM interception and message routing
- `replace.js`: JavaScript filter used by Bettercap to modify MQTT payload content
- `mqtt_tcp/`: ESP-IDF project with MQTT publisher setup for use in the attack

## Tools Used

- **tcpdump**: For capturing MQTT packets at different points
- **Wireshark**: For analyzing MQTT message contents
- **Ettercap**: For initial ARP spoofing MITM setup
- **Bettercap**: For more advanced MITM with packet modification
- **ESP32**: Publishes MQTT messages over Wi-Fi
- **Kali Linux**: Used as the attacker machine

## How to Run

1. Set up the IoT network (EdgeRouter X, Raspberry Pi with Mosquitto, ESP32 publisher, Kali Linux VM).
2. Use the ESP32 to publish messages using the provided `mqtt_tcp/` project.
3. Perform ARP spoofing from Kali using Ettercap or Bettercap.
