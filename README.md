# 🩺 IoT-Based COPD Monitoring System

Remote Health Monitoring for Chronic Obstructive Pulmonary Disease (COPD) Patients 

----------------------------------------------------------------------------------


## 📖 Project Overview

Chronic Obstructive Pulmonary Disease (COPD) is a progressive respiratory condition requiring continuous monitoring of vital signs.       
This project presents an IoT-powered COPD Monitoring System that:           
- Continuously tracks Oxygen Saturation (SpO₂) and Heart Rate (BPM).
- Uses embedded Linux (RuggedBoard A5D2X) for processing.
- Connects via WE10 WiFi module for cloud integration.
- Uploads data to Rightech IoT Cloud for real-time monitoring, visualization & automation.

✅ The solution enables remote health monitoring, reducing hospital visits and providing early detection of anomalies for COPD patients.  

## 🧩 Hardware & Components

| Component              | Role                       | Key Features                                                                         |
| ---------------------- | -------------------------- | ------------------------------------------------------------------------------------ |
| **MAX30102 Sensor**    | Measures SpO₂ & Heart Rate | PPG technique, red (660nm) & IR (880nm) LEDs, I2C communication, onboard temp sensor |
| **RuggedBoard A5D2X**  | Embedded Processing        | Linux-powered SBC, ARM Cortex-A5, I2C/UART support, real-time monitoring             |
| **WE10 WiFi Module**   | Connectivity               | Secure wireless data transmission to cloud                                           |
| **Rightech IoT Cloud** | Cloud Platform             | Data storage, visualization, automation, remote alerts                               |


## 💻  Embedded System - RuggedBoard A5D2X

The RuggedBoard A5D2X is aLinux-powered SingleBoard Computer (SBC) based on the Microchip SAMA5D27 ARM Cortex-A5 processor. Designed for industrial and edge computing, it provides robust processing capabilities and a wide range of peripheral interfaces including I2C and UART, making it suitable for real-time health monitoring applications.      
The board reads SpO2 and heart rate data from the MAX30102 sensor over I2C and formats the readings for transmission. Its ability to run full-featured Linux enables edge processing, local filtering of noise/artifacts, and even basic analytics if required.     

## 🏙  Sensor Module - MAX30102

The MAX30102 is an integrated pulseoximeter and heart-rate monitoring sensor developed by Maxim Integrated. It functions using the photoplethysmography (PPG) technique, where red (660 nm) and infrared (880 nm) LEDs illuminate human tissue, and a photodetector captures the reflected light.      
The sensor calculates:    
    - SpO2 using the absorption ratio of red and IR light.    
    - Heart Rate (BPM) using variations in the absorption due to blood pulsations.          
The sensor is compact, power-efficient, and communicates via the I2C interface. It also includes ambient light cancellation and an onboard temperature sensor for enhanced accuracy.  

## 🔬 System Architecture

flowchart TD
  Sensor(MAX30102 Sensor) -->|I2C| SBC[RuggedBoard A5D2X]
  SBC -->|WiFi (WE10)| Cloud[Rightech IoT Cloud]
  Cloud -->|Visualization| Doctor[Healthcare Providers]
  Cloud -->|Alerts| Patient[Patient Mobile App]

## 🛠 Working Principle

**1. Data Acquisition**      
    - MAX30102 uses PPG technique to measure SpO₂ and BPM.     
    - Photodetector captures reflected light variations caused by blood flow.   

**2. Embedded Processing**       
     - RuggedBoard A5D2X reads sensor data over I2C.    
     - Runs Linux-based scripts for preprocessing & noise filtering.   

**3. Cloud Integration**         
     - Processed data transmitted via WiFi (WE10 module).   
     - Stored & visualized on Rightech IoT Cloud dashboard.  

**4. Monitoring & Alerts**    
     - Doctors can view patient health remotely.      
     - Alerts triggered if vitals fall outside safe thresholds.     
