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

* Real-time underground cable fault detection
* Fault distance estimation using Ohm's Law
* 16×2 LCD display for local monitoring
* Buzzer and LED alerts
* IoT monitoring using ESP8266 and Blynk Cloud
* Three-phase cable fault simulation
* Embedded C firmware implementation
* Modular low-level driver design
* Reliable hardware validation and testing

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

<img width="711" height="728" alt="Hardware_Setup jpg" src="https://github.com/user-attachments/assets/d16c37dd-fd83-40d1-b7f9-93b533ec05da" />
** Complete hardware prototype of the IoT-Based Underground Cable Fault Detection System.

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

# Hardware Operation

The Arduino UNO continuously monitors the simulated underground cable network through relay-controlled cable lines. Fault conditions are manually generated using the switch panel. Once a fault is detected, the firmware calculates the approximate fault distance using ADC measurements based on Ohm's Law.

The calculated fault information is:
- Displayed on the 16×2 LCD
- Indicated through LEDs and buzzer
- Sent to the ESP8266 NodeMCU
- Uploaded to the Blynk Cloud for remote monitoring

---

## Circuit Diagram

<img width="711" height="728" alt="Circuit_Diagram png" src="https://github.com/user-attachments/assets/42bfff0e-67d0-4600-9001-68cd0ae6bcb0" />

The following schematic illustrates the complete electrical connections of the IoT-Based Underground Cable Fault Detection System.

### Circuit Description

The system consists of an Arduino UNO as the main controller, interfaced with three relay modules that simulate three underground cable phases (R, Y, and B). A resistor network is used to represent cable resistance, enabling fault distance estimation using Ohm's Law.

The Arduino continuously samples the voltage through its Analog-to-Digital Converter (ADC), calculates the fault distance, and displays the results on a 16×2 I2C LCD.

An ESP8266 NodeMCU communicates with the Arduino through serial communication and uploads fault information to the Blynk IoT Cloud. A buzzer and LED indicators provide immediate local alerts whenever a fault is detected.

## Hardware Connections

| Component | Interface |
|----------|-----------|
| Arduino UNO | Main Controller |
| ESP8266 NodeMCU | UART Communication |
| LCD 16×2 (I2C) | SDA, SCL |
| Relay Modules | Digital Output Pins |
| LED Indicators | Digital Output Pins |
| Buzzer | Digital Output Pin |
| Cable Resistance Network | Analog Input (ADC) |
| Power Supply Module | 5V / 12V DC |

## Embedded System Highlights

- Embedded C firmware developed for Arduino UNO
- ADC-based voltage measurement
- Ohm's Law based fault distance calculation
- UART communication between Arduino UNO and ESP8266
- I2C communication with 16×2 LCD
- Relay-based three-phase cable simulation
- Real-time IoT monitoring using Blynk Cloud
- Local fault indication using LEDs and buzzer

## Pin Configuration

| Device | Connection |
|---------|------------|
| LCD | I2C (SDA, SCL) |
| ESP8266 | UART (TX/RX) |
| Relay 1 | Digital Output |
| Relay 2 | Digital Output |
| Relay 3 | Digital Output |
| LEDs | Digital Output |
| Buzzer | Digital Output |
| Cable Network | Analog Input |

---

## LCD Output
<img width="1503" height="1600" alt="LCD_Fault jpg" src="https://github.com/user-attachments/assets/321fb29b-5560-44ad-8903-9345f7eca20c" />

The system displays the detected fault location and the corresponding cable phase on a 16×2 I2C LCD.

## Y Phase Fault

![LCD Y Fault](Images/LCD_Y_Fault.jpg)

The LCD indicates that the **Yellow (Y) phase** has a fault located approximately **6 km** from the feeder station.

---

## B Phase Fault

![LCD B Fault](Images/LCD_B_Fault.jpg)

The LCD indicates that the **Blue (B) phase** has a fault located approximately **7 km** from the feeder station.



---

## Blynk Dashboard

<img width="1486" height="1600" alt="Blynk_Dashboard jpg" src="https://github.com/user-attachments/assets/bcb00976-4131-43d2-8a35-67033ed567d3" />

The ESP8266 NodeMCU transmits real-time cable fault information to the Blynk Cloud Platform, allowing users to monitor the system remotely.

![Blynk Dashboard](Images/Blynk_Dashboard.jpg)

### Dashboard Features

- Displays the detected fault distance.
- Identifies the faulty cable phase.
- Shows normal operating status when no fault exists.
- Provides real-time monitoring through Wi-Fi.
---

# 📊 Experimental Results

The developed system successfully detected and localized faults in all three simulated underground cable phases.

| Test Case | Result |
|-----------|--------|
| R Phase Fault | ✅ Detected Successfully |
| Y Phase Fault | ✅ Detected Successfully |
| B Phase Fault | ✅ Detected Successfully |
| Fault Distance Calculation | ✅ Accurate |
| LCD Display | ✅ Working |
| LED Indication | ✅ Working |
| Buzzer Alert | ✅ Working |
| Blynk Cloud Update | ✅ Working |

The embedded firmware accurately estimated the fault distance based on voltage measurements and uploaded the results to the Blynk IoT Cloud in real time.

# Project Highlights

- Embedded C Firmware Development
- Arduino UNO Based Embedded System
- ESP8266 IoT Integration
- ADC-Based Fault Distance Calculation
- UART Communication
- I2C LCD Interface
- Relay-Based Three-Phase Fault Simulation
- Real-Time Cloud Monitoring
- Hardware Validation
- Functional Testing
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
## Lessons Learned

This project strengthened my understanding of:

- Embedded C programming
- Microcontroller interfacing
- ADC-based sensing
- UART and I2C communication
- IoT integration using ESP8266
- Hardware debugging and testing
- Firmware development and validation

# Author

**Shikhin G S**

Bachelor of Engineering (Electrical & Electronics Engineering)

**Skills:** Embedded C • C++ • Python • Embedded Systems • Firmware Development • IoT • UART • SPI • I2C • Git • Linux

If you found this project useful, consider giving it a ⭐ on GitHub.
