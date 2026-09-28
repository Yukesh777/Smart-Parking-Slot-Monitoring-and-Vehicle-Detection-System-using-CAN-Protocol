# 🚗 Smart Parking Slot Monitoring and Vehicle Detection System Using CAN Protocol

## 📌 Project Overview

The **Smart Parking Slot Monitoring and Vehicle Detection System Using CAN Protocol** is an embedded system-based project designed to automate parking slot monitoring and vehicle detection using multiple Electronic Control Units (ECUs) communicating through the **CAN (Controller Area Network) Protocol**.

In conventional parking systems, drivers spend more time searching for available parking spaces, which increases fuel consumption and traffic congestion. This project provides an intelligent solution by detecting vehicle presence in parking slots and displaying real-time parking availability.

The system uses sensors to detect whether a parking slot is occupied or free. The collected information is processed by microcontrollers and transmitted between different nodes using CAN communication. This project demonstrates automotive-level communication between ECUs, similar to modern vehicle systems.

---

# 🎯 Objectives

The main objectives of this project are:

- To design an automated parking monitoring system.
- To detect vehicle presence in individual parking slots.
- To implement communication between multiple ECUs using CAN Protocol.
- To display real-time parking slot availability.
- To control vehicle entry and exit automatically.
- To understand automotive communication protocols used in real-time applications.

---

# 💡 Problem Statement

In traditional parking systems:

- Drivers need to manually search for available parking spaces.
- It consumes more time and fuel.
- Manual monitoring requires more human effort.
- There is no real-time information about parking availability.

To overcome these problems, this project introduces an automated parking management system that detects vehicle occupancy and communicates parking information through CAN protocol.

---

# 🏗️ System Architecture

```
                    Parking Slot Sensors
                            |
                            |
                     Vehicle Detection ECU
                            |
                            |
                         CAN BUS
                            |
          ------------------------------------
          |                                  |
       ECU-1                              ECU-2
 Slot Monitoring                    Gate Controller
          |                                  |
          |                                  |
      LCD Display                      Servo Motor
 Parking Information               Automatic Gate
```

---

# ⚙️ Working Principle

### 1. Vehicle Detection

- IR sensors are placed in parking slots.
- Sensors continuously monitor the presence of vehicles.
- When a vehicle enters a slot, the sensor output changes.

### 2. Data Processing

- The microcontroller reads sensor values.
- It determines whether the parking slot is occupied or available.
- The processed data is converted into CAN messages.

### 3. CAN Communication

- CAN protocol is used for communication between ECUs.
- The transmitter ECU sends parking information through the CAN bus.
- The receiver ECU receives and processes the CAN message.

### 4. Display and Control

- The parking status is displayed on the LCD.
- If parking space is available, the gate opens automatically.
- Servo motor is controlled based on parking availability.

---

# 🔌 CAN Protocol Implementation

## What is CAN?

CAN (Controller Area Network) is a serial communication protocol mainly used in automotive applications for communication between Electronic Control Units (ECUs).

It provides:

- High reliability communication
- Noise immunity
- Multi-node communication
- Fast data transfer
- Error detection mechanism

---

## CAN Communication in This Project

In this project:

- Multiple microcontroller nodes communicate through CAN.
- Vehicle detection data is transmitted as CAN frames.
- The receiving ECU interprets the message and updates the parking status.

Example:

```
CAN Message:

ID        DATA

0x101     SLOT 1 OCCUPIED
0x102     SLOT 2 AVAILABLE
0x103     SLOT 3 OCCUPIED
```

---

# 🔧 Hardware Components Used

## 1. LPC21xx Microcontroller

- ARM7 based microcontroller.
- Used for processing sensor data and CAN communication.
- Controls LCD, sensors, and servo motor.

---

## 2. CAN Transceiver

- Provides physical layer communication between microcontroller and CAN bus.
- Converts logic signals into CAN differential signals.

---

## 3. IR Sensors

- Used for detecting vehicle presence.
- Provides digital output based on obstacle detection.

---

## 4. LCD Display

- Displays parking slot information.
- Shows available and occupied slots.

Example:

```
SMART PARKING

SLOT 1 : FULL
SLOT 2 : EMPTY
SLOT 3 : FULL
```

---

## 5. Servo Motor

- Used for automatic gate control.
- Opens when parking space is available.
- Closes when parking slots are full.

---

## 6. LEDs

- Indicate parking slot status.

Green LED  → Available Slot

Red LED → Occupied Slot

---

# 💻 Software Tools Used

| Tool | Purpose |
|------|---------|
| Embedded C | Firmware Development |
| Keil µVision | Code Compilation |
| Flash Magic | Microcontroller Programming |
| Proteus | Simulation |
| GitHub | Project Management |

---

# 📂 Project Modules

## Module 1: Vehicle Detection Module

Responsibilities:

- Reads sensor inputs.
- Detects vehicle presence.
- Sends slot status information.

---

## Module 2: CAN Communication Module

Responsibilities:

- CAN initialization.
- Message transmission.
- Message reception.
- Data processing.

---

## Module 3: Display Module

Responsibilities:

- LCD initialization.
- Display parking information.
- Update real-time status.

---

## Module 4: Gate Control Module

Responsibilities:

- Controls servo motor.
- Allows vehicle entry based on parking availability.

---

# 🔄 Data Flow

```
Sensor Input
      |
      |
Microcontroller Processing
      |
      |
CAN Message Transmission
      |
      |
Receiver ECU
      |
      |
LCD Display + Gate Control
```

---

# ✨ Features

✅ Automatic vehicle detection  
✅ Real-time parking slot monitoring  
✅ CAN based ECU communication  
✅ LCD status display  
✅ Automatic gate operation  
✅ Automotive communication implementation  
✅ Embedded C firmware development  
✅ Multi-controller architecture  

---

# 🚘 Applications

This project can be implemented in:

- Smart city parking systems
- Shopping mall parking areas
- Office parking management
- Automotive parking assistance systems
- Industrial vehicle management systems

---

# 📈 Advantages

- Reduces searching time for parking spaces.
- Minimizes fuel wastage.
- Provides accurate parking information.
- Reliable communication using CAN protocol.
- Reduces manual monitoring effort.

---

# 🔮 Future Enhancements

Future improvements include:

- IoT based remote parking monitoring.
- Mobile application integration.
- RFID based vehicle identification.
- Automatic payment system.
- Cloud database integration.
- AI based vehicle detection using cameras.

---

# 🧠 Skills Demonstrated

Through this project, the following technical skills were implemented:

- Embedded C Programming
- ARM7 Microcontroller Programming
- GPIO Interfacing
- LCD Interfacing
- Sensor Interfacing
- CAN Protocol Communication
- ECU Based System Design
- Debugging and Testing

---

# 👨‍💻 Developed By

## YUKESH S

**Electronics and Communication Engineering (ECE)**  
Embedded Systems Engineer

GitHub Profile:

https://github.com/Yukesh777


---

# ⭐ Conclusion

The **Smart Parking Slot Monitoring and Vehicle Detection System Using CAN Protocol** successfully demonstrates an automotive embedded application where multiple ECUs communicate efficiently using CAN technology.

This project provides practical knowledge of embedded programming, communication protocols, sensor interfacing, and real-time control systems, which are essential concepts in the automotive embedded industry.
