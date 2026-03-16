
# Sentinel V2V
### Intelligent Vehicle Safety & Anti‑Theft Communication System

Sentinel V2V is an embedded automotive safety platform that integrates **accident detection, theft protection, and vehicle‑to‑vehicle (V2V) communication**.

The system combines **STM32 sensor processing**, **NRF24L01 wireless communication**, and **IoT connectivity using ESP8266 with the Blynk platform** to create a real‑time safety network between vehicles.

---

## Key Features

### Accident Detection
Uses MPU6050 accelerometer data.

Accident triggered when:
- Total acceleration > **2.8g**
- Orientation change > **55°**

When triggered:
- Alert sent to nearby vehicles
- Notification sent to Blynk
- OLED shows accident warning

---

### Theft Detection
Uses vibration sensor (SW‑420).

Logic:
1. Vehicle locked via Blynk
2. Vibration detected
3. Theft alert triggered and notification sent

---

### Vehicle‑to‑Vehicle Communication
Wireless communication using **NRF24L01**.

Distance states:
- FAR
- NEAR
- VERY CLOSE

Vehicles broadcast accident alerts to nearby vehicles.

---

## System Architecture

MPU6050 -> STM32F411 -> ESP8266 -> NRF24L01 -> ESP32 Receiver -> OLED

ESP8266 also connects to **Blynk Cloud** for mobile monitoring.

---

## Hardware Components

- STM32F411CEU6
- ESP8266 NodeMCU
- ESP32
- NRF24L01
- MPU6050 Accelerometer
- SW420 Vibration Sensor
- SSD1306 OLED Display
- Relay module (proposed feature)

---

## Prototype Note

This implementation is a **hardware prototype using development boards**.
A **custom integrated PCB is currently under development** to miniaturize the system.

---

## Repository Structure

firmware/
- stm32_controller
- esp8266_transmitter
- esp32_receiver

docs/
- architecture diagram
- algorithm explanation

hardware/
- components list
- pin connections

demo/
- prototype images
- OLED output
- Blynk interface

---

## Technologies

Embedded: STM32 HAL  
Wireless: NRF24L01  
IoT: ESP8266 + Blynk  
Sensors: MPU6050 + SW420  
Language: C / Arduino

