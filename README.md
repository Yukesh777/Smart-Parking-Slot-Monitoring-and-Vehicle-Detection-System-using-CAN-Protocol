Smart Parking Slot Monitoring and Vehicle Detection System Using CAN Protocol
1. Project Overview

The Smart Parking Slot Monitoring and Vehicle Detection System is an embedded system designed to monitor parking-slot occupancy and manage vehicle entry and exit automatically. The system uses LPC2129 ARM7 microcontrollers, IR sensors, CAN communication, an RTC, LCD display, and a servo motor.

Three nodes are used to monitor different parking areas. Each node detects whether a parking slot is occupied or free using IR sensors and sends the status to the main monitoring node through the CAN bus. The system calculates the available parking spaces and displays the information on an LCD. A servo motor is used to control the entrance gate based on parking availability.
2. Objective

The main objectives of the project are:

    To detect vehicles entering and leaving parking slots automatically.

    To monitor multiple parking slots in real time.

    To communicate parking information between multiple controllers using CAN protocol.

    To display the number of available and occupied slots on an LCD.

    To automatically control the parking entrance gate using a servo motor.

    To record vehicle entry and exit time using an RTC.

    To reduce manual monitoring and improve parking management.

3. System Architecture

The system consists of three LPC2129-based nodes connected through a CAN communication network.

    Node 1: Monitors the first set of parking slots.

    Node 2: Monitors the second set of parking slots.

    Node 3: Acts as the main monitoring/control node and manages the gate, LCD and overall parking information.

The IR sensors detect the presence of vehicles. Each LPC2129 processes its sensor information and transmits the parking status through the CAN bus. Node 3 receives the information and updates the total parking status.

Overall flow:

IR Sensors → LPC2129 Nodes → CAN Bus → Main Node → LCD / Servo Gate / RTC
4. Node 1

Node 1 is responsible for monitoring the parking slots assigned to the first parking section.

IR sensors are connected to the GPIO pins of the LPC2129. When a vehicle enters a slot, the corresponding IR sensor detects the vehicle and the microcontroller identifies the slot as occupied.

Node 1 generates a CAN message containing the parking-slot status and transmits it to the main node through the CAN transceiver.

Functions of Node 1:

    Read IR sensors.

    Detect vehicle presence.

    Determine occupied/free slots.

    Generate CAN messages.

    Transmit slot status to Node 3.

5. Node 2

Node 2 performs the same monitoring operation for another group of parking slots.

The LPC2129 continuously reads the IR sensors connected to its parking slots. The detected information is processed and transmitted to the main controller using the CAN communication network.

Functions of Node 2:

    Monitor assigned parking slots.

    Detect vehicle presence using IR sensors.

    Process sensor information.

    Send parking status through CAN.

    Update the main controller about slot availability.

6. Node 3

Node 3 acts as the main control and monitoring node of the system.

It receives parking information from Node 1 and Node 2 through CAN communication. It combines the received information with its own sensor information to determine the overall parking status.

Node 3 controls the LCD display and servo motor. If parking spaces are available, the gate can be opened when a vehicle approaches. If all slots are occupied, the system can prevent entry and display a "PARKING FULL" message.

The RTC is used to maintain the current date and time for recording vehicle entry and exit events.
7. What Is Implemented

The following features are implemented in the project:

    Multiple parking-slot monitoring.

    Vehicle detection using IR sensors.

    Three LPC2129 microcontroller nodes.

    CAN-based communication between nodes.

    Parking-slot occupancy calculation.

    LCD-based parking-status display.

    Automatic gate control using a servo motor.

    RTC-based time monitoring.

    Centralized parking information management.

    Real-time communication between parking nodes.

8. Working Principle

When a vehicle approaches the parking system, the IR sensors detect its presence.

    The IR sensor produces a digital signal depending on whether a vehicle is present.

    The corresponding LPC2129 reads the sensor status.

    The node determines whether the parking slot is occupied or free.

    The slot information is packed into a CAN data frame.

    The CAN transceiver transfers the data through the CAN bus.

    Node 3 receives the information from the other nodes.

    Node 3 calculates the total number of occupied and available slots.

    The parking status is displayed on the LCD.

    If space is available, the servo motor operates the entrance gate.

    The RTC provides the current time for vehicle entry/exit monitoring.

9. Block Diagram

              ┌───────────────────┐
              │    IR Sensors     │
              │    Parking Area 1 │
              └─────────┬─────────┘
                        │
                        ▼
                ┌──────────────┐
                │   NODE 1     │
                │   LPC2129    │
                └──────┬───────┘
                       │
                       │ CAN
                       │
                       ▼
        ╔══════════════════════════════╗
        ║          CAN BUS             ║
        ╚══════════════════════════════╝
                       │
              ┌────────┴────────┐
              │                 │
              ▼                 ▼
       ┌──────────────┐  ┌──────────────┐
       │   NODE 2     │  │   NODE 3     │
       │   LPC2129    │  │   LPC2129    │
       └──────┬───────┘  └──────┬───────┘
              │                 │
              │                 ├──────────► LCD
              │                 │
              │                 ├──────────► Servo Motor
              │                 │
              │                 └──────────► RTC
              │
              ▼
       ┌─────────────────┐
       │ IR Sensors      │
       │ Parking Area 2  │
       └─────────────────┘

10. Hardware Components

The major hardware components used are:
LPC2129

ARM7-based microcontroller used as the processing unit for each parking node.
IR Sensors

Used to detect the presence or absence of vehicles in parking slots.
CAN Transceiver

Used to provide physical-layer communication between the LPC2129 nodes and the CAN bus. An MCP2551 can be used as the CAN transceiver.
LCD

A 16×2 LCD is used to display parking information such as:

    Available slots

    Occupied slots

    Parking full status

    Entry/exit information

Servo Motor

Used to control the parking entrance gate automatically.
RTC

The Real-Time Clock maintains date and time information for recording vehicle entry and exit events.
Power Supply

Provides the required regulated voltage to the microcontrollers, sensors, CAN transceivers, LCD and other peripherals.
11. Software Components

The software is developed using embedded C.
Development Tools

    Keil µVision 4

    Embedded C

    LPC2129 startup code

    Proteus for simulation

Software Modules

    GPIO initialization

    IR sensor interface

    LCD driver

    CAN initialization

    CAN transmit function

    CAN receive function

    RTC driver

    Servo motor control

    Parking-slot counting logic

    Main control program

    Delay/timer functions

12. Communication

The communication between the three LPC2129 nodes is performed using the Controller Area Network (CAN) protocol.

Each node generates CAN messages containing parking-slot information. The CAN transceiver converts the controller's CAN signals into the electrical signals required for transmission over the CAN bus.

The main node receives the messages and processes the information.

Node 1 ───────┐
              │
              ▼
          CAN BUS
              │
              ▼
Node 2 ───────┤──────► Node 3
              │
              ▼
        Parking Status

CAN provides reliable multi-node communication and is suitable for embedded systems because it supports message-based communication and error detection.
13. Project Features

    Automatic vehicle detection.

    Multiple parking-slot monitoring.

    Three-node distributed architecture.

    CAN-based communication.

    Real-time parking-status monitoring.

    Automatic gate control.

    LCD status display.

    RTC-based time monitoring.

    Centralized parking management.

    Reduced human intervention.

    Suitable for embedded-system applications.

14. Advantages

    Reduces manual work: Parking slots can be monitored automatically.

    Real-time monitoring: Slot status can be updated continuously.

    Reliable communication: CAN provides robust communication between nodes.

    Scalable architecture: Additional nodes and parking slots can be added.

    Automatic gate control: Reduces the need for manual gate operation.

    Low-cost implementation: Uses commonly available embedded-system components.

    Improved parking efficiency: Drivers can identify available parking spaces quickly.

    Fault detection: CAN provides built-in error detection mechanisms.

15. Applications

The system can be used in:

    Shopping malls

    IT parks

    Colleges and universities

    Hospitals

    Airports

    Railway stations

    Office parking areas

    Apartment complexes

    Smart-city parking systems

    Industrial parking areas

16. Future Scope

The project can be further improved by adding advanced features such as:

    IoT connectivity for remote parking monitoring.

    Mobile application to display available parking slots.

    Cloud database for storing parking records.

    RFID-based vehicle identification.

    Automatic number plate recognition (ANPR).

    Online parking-slot reservation.

    Payment and billing system.

    Web-based parking management dashboard.

    Camera-based vehicle detection.

    AI-based parking prediction.

    Integration with smart-city infrastructure.

    Expansion to a larger number of parking nodes and slots.

17. Conclusion

The Smart Parking Slot Monitoring and Vehicle Detection System using CAN Protocol provides an automated and reliable method for managing parking spaces. The combination of LPC2129 microcontrollers, IR sensors, CAN communication, LCD, RTC and servo motor enables real-time monitoring, vehicle detection and automatic gate control. The modular three-node architecture also provides a foundation for expanding the system into a larger IoT-enabled smart parking solution.


