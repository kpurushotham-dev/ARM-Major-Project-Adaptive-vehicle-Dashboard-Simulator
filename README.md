
#  ARM Major Project – Adaptive Vehicle Dashboard Simulator

##  Overview

This project simulates a vehicle dashboard system using the **ARM7 LPC2129 microcontroller** and **CAN protocol communication** between two nodes.The system is designed with a dual-node architecture to demonstrate real-time vehicle data acquisition, processing, and display.

## System Architecture

### -> NODE_A – Sensor Node (Transmitter)

- **Microcontroller:** LPC2129 (ARM7)
- **Sensors Interfaced:**
  - LM35 Temperature Sensor  (Temperature measurement)
  - Ultrasonic Sensor HC-SR04  (fuel measurement)
  - Potentiometer – Speed 
- **Communication:** CAN Protocol (CAN1)
- **Function:** Reads sensor data, processes it, and transmits the data through the CAN bus.

### -> NODE_B – Dashboard Node (Receiver)

- **Microcontroller:** LPC2129 (ARM7) 
- **Display:** PC Terminal via UART
- **Communication:** CAN Protocol
- **Function:** Receives CAN data from Node A and displays vehicle parameters such as:
  - Speed
  - Temperature
  - Distance
  - Fuel

##  Hardware Used

- LPC2129 ARM7 Development Boards – 2
- MCP2551 CAN Transceivers
- HC-SR04 Ultrasonic Sensor
- LM35 Temperature Sensor
- Potentiometer
- Connecting Wires

##  Software & Drivers

- **adc_driver.c / .h** – ADC and Ultrasonic sensor interfacing
- **can1_driver.c / .h** – CAN1 initialization and transmission (125 kbps)
- **delay.c / .h** – Microsecond, millisecond, and second delay functions
- **uart_driver.c** – UART communication for PC display (9600 baud)
##  CAN Protocol Configuration


- **Microcontroller:** LPC2129 ARM7
- **CAN Bit Rate:** 125 kbps
- **Peripheral Clock (PCLK):** 60 MHz (VPBDIV = 1)
- **Frame Type:** Standard Data Frame
- **Communication:** CAN Bus
- **UART Baud Rate:** 9600 bps

##  How It Works

1. **Temperature Measurement:** Node A reads temperature from the LM35 sensor through ADC (CH0).
2. **Fuel Measurement:** Node A measures distance using the HC-SR04 Ultrasonic sensor with Timer Capture.
3. **Speed Measurement:** Node A reads the potentiometer input to simulate vehicle speed.
4. **Data Processing:** The LPC2129 processes the acquired sensor values.
5. **CAN Transmission:** Node A packs the sensor data into a CAN frame and transmits it through the CAN bus.
6. **CAN Reception:** Node B receives the CAN frame using a CAN interrupt service routine (ISR).
7. **Dashboard Display:** Node B displays the received vehicle parameters on the  terminal through UART.


##  Applications

- Automotive embedded systems
- Smart vehicle dashboard monitoring
- Real-time sensor data acquisition
- CAN-based ECU communication
- Automotive electronics development

##  Future Enhancements

- Real-time fuel level monitoring
- GPS-based vehicle tracking
- Wireless vehicle monitoring
- Advanced vehicle safety alerts
- Graphical dashboard interface

##  Skills Gained

- Embedded C Programming
- ARM7 LPC2129 Microcontroller
- ADC Interfacing
- Sensor Interfacing
- CAN Protocol Communication
- UART Communication
- Interrupt Handling
- Embedded Driver Development

##  Conclusion

The Adaptive Vehicle Dashboard Simulator demonstrates the implementation of a dual-node automotive monitoring system using ARM7 LPC2129 microcontrollers and CAN communication.

The project provides practical experience in real-time sensor interfacing, embedded driver development, CAN data transmission, interrupt handling, and vehicle parameter monitoring.

---

**Project Domain:** Embedded Systems | Automotive Electronics | ARM7 | Embedded C | CAN Protocol

**Controller:** LPC2129 ARM7
