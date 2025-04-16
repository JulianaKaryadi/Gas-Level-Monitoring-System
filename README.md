# Gas-Level-Monitoring-System
ESP32-based Gas Level Monitoring System using MQ-2 sensor with Blynk integration for real-time residential gas leak detection and alerts.

## Overview
This project implements a real-time gas level monitoring system using an ESP32 microcontroller and MQ-2 gas sensor. The system is designed to enhance household safety by providing continuous monitoring of combustible gases, displaying real-time gas levels on an LCD, triggering audible alerts when dangerous levels are detected, and enabling remote monitoring via the Blynk mobile application.

![System Architecture](https://github.com/user-attachments/assets/455cd5af-cf3d-4406-8fd6-b46ce802bdfe)

## Features
- Real-time gas level detection using MQ-2 sensor
- Local display of gas levels on LCD screen
- Audible alarm via buzzer when gas levels exceed safety threshold
- Remote monitoring capabilities through Blynk cloud platform
- Easy installation and configuration
- Low-cost and reliable solution for residential safety

## Hardware Components
- ESP32 DEVKITV1 Development Board
- MQ-2 Gas Sensor
- 16x2 LCD Display with I2C Interface
- 5V Buzzer
- Jumper Wires
- USB Cable for Power

## Software Requirements
- Arduino IDE
- Required Libraries:
  - LiquidCrystal_I2C
  - Wire
  - WiFiClient
  - BlynkSimpleEsp32

## Circuit Connections
- MQ-2 Gas Sensor:
  - VCC → 3.3V pin on ESP32
  - GND → GND pin on ESP32
  - AO (Analog Output) → VP (GPIO34) pin on ESP32

- 5V Buzzer:
  - Positive terminal → VIN pin on ESP32
  - Negative terminal → GND pin on ESP32

- I2C Module and LCD Screen:
  - VCC → 3.3V pin on ESP32
  - GND → GND pin on ESP32
  - SDA → D21 (SDA) pin on ESP32
  - SCL → D22 (SCL) pin on ESP32

## Usage
1. Power up the system using a USB cable
2. The LCD will display "System Loading" during initialization
3. After initialization, the system will start monitoring gas levels
4. The LCD will display the current gas level and status (Normal/Warning)
5. If gas levels exceed 50%, the buzzer will sound and the LED widget in the Blynk app will turn on
6. Monitor gas levels remotely using the Blynk app

## Code Overview
The system continuously reads analog values from the MQ-2 sensor, maps them to a percentage (0-100%), and displays this information on the LCD. When gas levels exceed the threshold (50%), it triggers the buzzer and sends alerts through Blynk. The main components of the code include:

- Setup: Initializes communication with Blynk, LCD, and configures pins
- GASLevel function: Reads sensor values, maps them, and triggers alerts when necessary
- Loop: Continuously runs the GASLevel function and Blynk processes

## Contributors
- Juliana Binti Karyadi (52213122054)
- Farisa Binti Haslan Farouk (52213122108)
- Nurfatihah Syafiqah Binti Mohd Rosli (52213122181)
