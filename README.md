# INS_survey_USV

An open-source autonomous unmanned surface vessel (USV) for inland waterway surveying. This platform combines inertial navigation, GPS, sonar, and intelligent control for accurate 3D mapping in shallow waters.

## Project Overview

This boat is designed for:
- Autonomous navigation to waypoints
- Real-time inertial navigation and GPS fusion
- Underwater depth mapping up to 50 feet
- Low-cost and lightweight construction
- Expandability for environmental monitoring or industrial use

---

## Features

- **INS-based navigation** using gyroscope + accelerometer
- **GPS + Magnetometer fusion** for heading correction
- **Single motor + rudder system** using PCA9685 servo control
- **Obstacle logic** via software (expandable with sensors)
- **Optional star tracker** for nighttime orientation
- **Centralized logging** of all navigation and sensor data
- **Custom hull** (6' lightweight and unsinkable design)
- **Raspberry Pi 4-based controller** running headless

---

## Hardware Components

| Component                     | Description                        |
|------------------------------|------------------------------------|
| Raspberry Pi 4               | Core controller                    |
| MPU6050 or BNO055            | Accelerometer + Gyroscope          |
| NEO-M8N GPS + QMC5883L       | GPS with magnetometer              |
| PCA9685                      | PWM driver for motor + rudder      |
| Servo Motor + Rudder         | Manual steering via PWM            |
| Brushless DC Motor + ESC     | Propulsion                         |
| Depth Sonar (e.g., Ping Sonar)| Water depth mapping                |
| Waterproof Button            | Start/Stop/Abort input             |
| Power Supply (battery pack)  | Boat power                         |
| Custom Hull                  | 6’ V-shape, stable platform        |

---

## Software

All source code is located in this repo:
- `main.py` – launches INS loop, GPS, logging, and controls
- `ins.py` – calculates position from IMU data
- `gps_mag.py` – interfaces GPS + magnetometer
- `motor_control.py` – controls motor and rudder
- `button_control.py` – handles start, stop, abort button logic
- `logger.py` – writes all data to timestamped log
- `star_tracker.py` – (optional) celestial nav system
- `requirements.txt` – all Python dependencies
- `config.json` – settings like GPIO pins and thresholds

---

## Installation

```bash
sudo apt update
sudo apt install python3-pip
pip3 install -r requirements.txt
