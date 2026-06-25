# IoT-Based Underground Cable Fault Detection System

## Overview

The **IoT-Based Underground Cable Fault Detection System** is an embedded systems project designed to automatically detect, locate, and report faults in underground power cables. The system uses an **Arduino UNO** as the primary controller and an **ESP8266 NodeMCU** for IoT communication.

The fault detection algorithm is based on **Ohm's Law (V = IR)**. By measuring voltage variations using the Arduino's **10-bit ADC**, the system estimates the location of cable faults and displays the results on a **16×2 LCD** while simultaneously sending real-time updates to the **Blynk IoT Cloud**.

This project demonstrates embedded firmware development, hardware interfacing, ADC processing, UART communication, IoT integration, and real-time monitoring.

---

# Objectives

* Detect underground cable faults automatically.
* Estimate fault distance from the feeder station.
* Reduce manual inspection time.
* Provide real-time monitoring through IoT.
* Improve maintenance efficiency for underground electrical distribution systems.

---

# Features

* ✅ Real-time underground cable fault detection
* ✅ Fault distance estimation using Ohm's Law
* ✅ 16×2 LCD display for local monitoring
* ✅ Buzzer and LED alerts
* ✅ IoT monitoring using ESP8266 and Blynk Cloud
* ✅ Three-phase cable fault simulation
* ✅ Embedded C firmware implementation
* ✅ Modular low-level driver design
* ✅ Reliable hardware validation and testing

---

# Working Principle

The project operates using the principle of **Ohm's Law (V = IR)**.

1. DC voltage is applied to the simulated underground cable.
2. Cable resistance changes depending on the fault location.
3. The Arduino UNO reads the voltage using its 10-bit ADC.
4. Embedded firmware processes the ADC values.
5. The system calculates the approximate fault distance.
6. Fault information is displayed on the LCD.
7. The ESP8266 sends the data to the Blynk Cloud.
8. Users receive live fault updates on their mobile device.

---

# Fault Types Supported

* Open Circuit Fault
* Short Circuit Fault
* Line-to-Ground (L-G)
* Line-to-Line (L-L)

---

# Hardware Components

| Component              | Description                              |
| ---------------------- | ---------------------------------------- |
| Arduino UNO            | Main microcontroller for fault detection |
| ESP8266 NodeMCU        | Wi-Fi communication module               |
| 3-Channel Relay Module | Three-phase fault simulation             |
| Resistors              | Simulate cable resistance per kilometer  |
| 16×2 LCD               | Displays fault distance and status       |
| Buzzer                 | Audible fault alert                      |
| LEDs                   | Visual fault indication                  |
| SPDT Switches          | Manual fault simulation                  |
| 12V Power Supply       | System power source                      |

---

# Software Requirements

* Arduino IDE
* Embedded C / C++
* ESP8266 Libraries
* Blynk IoT Platform
* Proteus (Optional)

---

# Embedded Concepts Used

* Embedded C Programming
* Firmware Development
* ADC Interfacing
* UART Communication
* I2C LCD Interface
* Relay Driver Control
* Software Serial Communication
* Interrupt-Based Processing
* Modular Driver Design
* Hardware Validation
* Functional Testing
* Embedded Debugging
* IoT Integration

---

# IoT Integration

The ESP8266 NodeMCU connects the Arduino system to the **Blynk IoT Cloud**.

Users can:

* Monitor system status remotely
* View fault distance
* Identify the faulty cable phase
* Receive instant notifications
* Access data from mobile or web dashboard

---

# System Architecture

```text
                  +-------------------+
                  |   Power Supply    |
                  +-------------------+
                           |
                           v
                  +-------------------+
                  |   Arduino UNO     |
                  +-------------------+
                    |      |      |
                    |      |      |
             ADC    |      |   UART
                    |      |      |
                    v      |      v
             Cable Network |  ESP8266 NodeMCU
                    |      |      |
                    |      |      |
               Relay Module | Wi-Fi
                    |      |      |
                    v      |      v
                LCD Display | Blynk Cloud
                    |              |
                    v              v
              Buzzer & LED   Mobile Dashboard
```

---

# Project Workflow

```text
Start

↓

Initialize Arduino

↓

Initialize LCD

↓

Initialize ESP8266

↓

Read ADC Value

↓

Calculate Voltage

↓

Apply Ohm's Law

↓

Estimate Fault Distance

↓

Display on LCD

↓

Send Data to ESP8266

↓

Upload to Blynk Cloud

↓

Activate Buzzer

↓

Repeat
```

---

# Circuit Block Diagram

```text
Power Supply
      │
      ▼
Arduino UNO
      │
 ├── ADC
 ├── LCD
 ├── Relay Module
 ├── Buzzer
 ├── LEDs
 │
 ▼
ESP8266 NodeMCU
 │
 ▼
Wi-Fi
 │
 ▼
Blynk Cloud
 │
 ▼
Mobile Application
```

---

# Project Structure

```text
IoT-Underground-Cable-Fault-Detection/

│
├── README.md
├── Arduino_Code/
├── ESP8266_Code/
├── Circuit_Diagram/
├── Images/
│   ├── Hardware_Setup.jpg
│   ├── Circuit_Diagram.png
│   ├── LCD_Output.jpg
│   ├── Blynk_Dashboard.jpg
│   └── Working_Model.jpg
├── Documentation/
├── LICENSE
```

---

# Project Images

## Hardware Setup

<img alt="Hardware_Setup jpg" src="https://github.com/user-attachments/assets/d16c37dd-fd83-40d1-b7f9-93b533ec05da" />

The figure below shows the complete hardware prototype developed for the IoT-Based Underground Cable Fault Detection System.

### Hardware Description

The hardware prototype consists of:

- Arduino UNO (Main Controller)
- ESP8266 NodeMCU (IoT Communication)
- 16×2 I2C LCD Display
- Relay Modules for Three-Phase Cable Simulation
- LED Status Indicators
- Piezo Buzzer
- SPDT Switches for Fault Simulation
- DC Power Supply Module
- Custom PCB for Driver Circuit



---

## Circuit Diagram

(Add circuit diagram here)

---

## LCD Output

(Add LCD image here)

---

## Blynk Dashboard

(Add dashboard screenshot here)

---

# Results

| Test                    | Status   |
| ----------------------- | -------- |
| Open Circuit Detection  | ✅ Passed |
| Short Circuit Detection | ✅ Passed |
| Line-to-Ground Fault    | ✅ Passed |
| Line-to-Line Fault      | ✅ Passed |
| LCD Display             | ✅ Passed |
| Buzzer Alert            | ✅ Passed |
| IoT Dashboard Update    | ✅ Passed |
| Three-Phase Simulation  | ✅ Passed |

---

# Demonstration

A short demonstration video showing:

* Hardware setup
* Fault simulation
* LCD output
* Buzzer activation
* Real-time Blynk dashboard update

(Add YouTube video link here.)

---

# Future Improvements

* GSM/SMS alert system
* GPS-based fault localization
* Predictive maintenance using Machine Learning
* Cloud database integration
* Web dashboard for utilities
* Solar-powered operation
* Mobile application
* Support for larger underground cable networks

---

# Technologies Used

* Embedded C
* Arduino UNO
* ESP8266 NodeMCU
* UART Communication
* ADC Interfacing
* I2C Communication
* Relay Control
* Embedded Firmware Development
* Blynk IoT Cloud
* Git & GitHub
* Arduino IDE

---

# Author

**Shikhin G S**

Bachelor of Engineering (Electrical & Electronics Engineering)

**Skills:** Embedded C • C++ • Python • Embedded Systems • Firmware Development • IoT • UART • SPI • I2C • Git • Linux

If you found this project useful, consider giving it a ⭐ on GitHub.
