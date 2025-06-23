# IoT-Based-COPD-Monitoring-Report
This project presents a remote health monitoring solution for patients with Chronic Obstructive Pulmonary Disease (COPD). It utilizes IoT technologies to continuously measure and monitor critical vital signs — specifically oxygen saturation (SpO₂) and heart rate data via I2C using MRAA on embedded Linux.

    Project Overview
Chronic Obstructive Pulmonary Disease (COPD) is a progressive respiratory condition requiring frequent
monitoring of critical vital signs, particularly oxygen saturation (SpO2) and heart rate. This project introduces
a comprehensive IoT-based COPD monitoring system that leverages the MAX30102 optical sensor,
RuggedBoard A5D2X for embedded processing, WE10 WiFi module for connectivity, and Rightech IoT Cloud
for cloud-based monitoring, visualization, and automation.

    Sensor Module - MAX30102
TheMAX30102 is an integrated pulseoximeter and heart-rate monitoring sensor developed by Maxim
Integrated. It functions using the photoplethysmography (PPG) technique, where red (660 nm) and infrared
(880 nm) LEDs illuminate human tissue, and a photodetector captures the reflected light. The sensor
calculates:
    - SpO2 using the absorption ratio of red and IR light.
    - Heart Rate (BPM) using variations in the absorption due to blood pulsations.
    The sensor is compact, power-efficient, and communicates via the I2C interface. It also includes ambient light cancellation and an onboard temperature sensor for enhanced accuracy.

    Embedded System - RuggedBoard A5D2X
The RuggedBoard A5D2X is aLinux-powered SingleBoard Computer (SBC) based on the Microchip SAMA5D27
ARM Cortex-A5 processor. Designed for industrial and edge computing, it provides robust processing
capabilities and a wide range of peripheral interfaces including I2C and UART, making it suitable for real-time
health monitoring applications.
The board reads SpO2 and heart rate data from the MAX30102 sensor over I2C and formats the readings for
transmission. Its ability to run full-featured Linux enables edge processing, local filtering of noise/artifacts,
and even basic analytics if required
