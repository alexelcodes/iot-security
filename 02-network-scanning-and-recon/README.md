# Network Scanning and Reconnaissance

## Overview

This project focuses on network protocol analysis, traffic capture, and active reconnaissance using tools available in Kali Linux.

It is divided into two parts:

- **Part A** analyzes ARP, ICMP, and TCP traffic using Wireshark and `tcpdump`
- **Part B** discovers devices, services, and vulnerabilities using Nmap and OpenVAS

The goal is to identify potential weaknesses in an IoT network environment.

## Key Features

- Uses `arp`, Wireshark, and `tcpdump` to analyze LAN traffic
- Captures MQTT messages and TCP SYN packets
- Scans the network with Nmap (basic and full scans with `vuln` scripts)
- Identifies and analyzes weaknesses using OpenVAS reports
- Documents findings with markdown files, PlantUML diagrams, and screenshots

## Project Files

The project includes the following files:

- `mqtt_tcp/`: ESP32 project publishing MQTT messages to the broker
- `mqtt-capture.md`: Captured MQTT message from `tcpdump`
- `tcp-syn-packet.md`: Hex dump of TCP SYN packet from Wireshark
- `arp-tables.md`: ARP table snapshots from devices
- `nmap-basic-scan.txt`, `nmap-full-scan.txt`: Results from basic and full Nmap scans
- `nmap-weakness-analysis.md`: AI-assisted analysis of Nmap scan
- `openvas-report-*.csv`: Vulnerability scan reports from OpenVAS
- `openvas-weakness-analysis.md`: Summary and interpretation of OpenVAS findings
- `reconnassaince-topology.plantuml`: Visual diagram of scanned network

## How to Build and Run the ESP32 Project

1. Set up the ESP-IDF environment:

   ```sh
   . $HOME/esp/esp-idf/export.sh
   ```

2. Build the project:

   ```sh
   cd mqtt_tcp
   idf.py build
   ```

3. Flash the firmware:

   ```sh
   idf.py flash
   ```

4. Monitor the serial output:

   ```sh
   idf.py monitor
   ```

## Notes

- The `docker-compose.yml` file used for container IP configuration is included.
- Traffic was captured both on Kali Linux using Wireshark and inside the Mosquitto container on Raspberry Pi using tcpdump.
- Scanning was performed from Kali Linux with modified routing to ensure symmetric visibility of traffic.
