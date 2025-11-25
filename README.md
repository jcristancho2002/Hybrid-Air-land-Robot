# Hybrid-Air-land-Robot
This repository contains the code, mechanical drawings, firmware configurations, and analysis scripts used in the development of the project:  **“Approach to the Design of a Hybrid Air-Land Robot '**

---

##  System Capabilities

### **Aerial subsystem**
- Quad-motor propulsion using ECO II 2807–1300KV brushless motors  
- Flight stabilization and PID control via Betaflight 4.5.0  
- GNSS + compass for positioning and orientation  
- Telemetry and failsafe mechanisms enabled  

### **Ground subsystem**
- 4 × DC metal-gear TT motors  
- Controlled through L298N + ESP32 PWM  
- Designed for indoor laboratory testing on flat terrain  

### **Transformation subsystem**
- 8 × 20 kg·cm digital servos  
- Actuated via PCA9685 (16-channel, 12-bit resolution)  
- Supports seamless transitions between ground and aerial modes  

### **Onboard computing**
- ESP32 for terrestrial logic, servo sequencing, and monitoring  
- Serial communication with the flight controller  
- Voltage and state supervision  

### **Energy analysis**
- Complete current–voltage–power matrices for all operating modes  
- Autonomy estimates for:
  - Ground mode  
  - Hover  
  - Elevation  
  - Mixed operation with transformation steps  

### **Mechanical design**
- Full Fusion 360 CAD files  
- Optimized PETG-CF frame for strength-to-weight ratio  
- STL files ready for additive manufacturing  

---

##  ESP32 Embedded Firmware – Functional Description

The ESP32 program is fully modular and divided into four major subsystems:

### 1. **Peripheral Initialization**
- PWM setup for motor control  
- I²C communication with PCA9685  
- Configuration of timing, frequency, and GPIO direction  
- Startup diagnostics through serial console  

### 2. **Ground Traction Control**
- Forward, reverse, and braking logic for 4 DC motors  
- PWM-based speed modulation  
- Designed for stable indoor operation on smooth floors  

### 3. **Servo Control**
- Conversion of target angles to 12-bit PWM signals  
- Smooth transitions using staged timing  
- Avoidance of current spikes by staggering servo activation  

### 4. **Structural Transition Logic**
- Automated transformation between ground and aerial modes  
- Triggered via:
  - Remote switch  
  - Serial command  
  - Physical button  
- Includes protection logic and voltage supervision  

The full firmware is included in `/firmware_esp32/`.

---

## 🔧 Flight Controller Configuration (Betaflight 4.5.0)

Included in this repository:

- **Complete Betaflight dump (`betaflight_dump_2025.txt`)**
- **UART mapping** (GPS via UART5 at 115200 baud)
- **Receiver setup** (CRSF — ExpressLRS)
- **Failsafe configuration**
- **OSD setup**
- **Blackbox activation**

Sensors detected:

- Gyro/ACC: ICM42688P  
- Barometer: BMP280  
- Magnetometer: QMC5883  
- GPS: u-blox M10  

---


##  Mechanical Files (Fusion 360 + STL)

The directory `mechanical_design/` includes:

- Editable Fusion 360 (.f3d) files  
- Final optimized assembly  
- STL files ready for printing  
- Exploded views for reporting and documentation  

---



## 🔗 Repository Link

**https://github.com/JuanCristancho/Hybrid Air-Land-Robot**

---
**Juan José Cristancho Chaparro**  
Electronic Engineering – Universidad de los Andes  
Email: *j.cristancho@uniandes.edu.co*  

---
