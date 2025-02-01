# ESP32 Motion Detection System

## Overview
This project, **MoveSense ESP**, is designed to classify motion types (e.g., Forward and Spin) using an **ESP32** microcontroller with an **MPU6050** sensor and a **TensorFlow Lite** machine learning model. The system reads real-time accelerometer and gyroscope data, processes it through a trained ML model, and outputs the detected motion.

## Features
- Real-time motion detection using MPU6050
- Machine learning inference on ESP32 with TensorFlow Lite for Microcontrollers (TFLM)
- Lightweight neural network for embedded systems
- Serial output of predicted motion type

## Hardware Requirements
- ESP32 Development Board
- MPU6050 Accelerometer & Gyroscope Sensor
- USB Cable for programming
- Computer with Arduino IDE or PlatformIO

## Software Requirements
- **Arduino IDE** or **PlatformIO**
- **MPU6050 Library** (`MPU6050` by Electronic Cats)
- **TensorFlow Lite for Microcontrollers (TFLM)**
- Python (for training and converting the model to TFLite)

## Installation & Setup
### 1. Install Required Libraries
Install the required Arduino libraries via **Library Manager**:
- `MPU6050` by Electronic Cats
- `TensorFlow Lite for Microcontrollers`

### 2. Upload the ESP32 Code
- Open `esp32_mpu6050_tflite.ino` in Arduino IDE
- Connect the ESP32 to your computer
- Select the correct board (`ESP32 Dev Module`) and port
- Click **Upload**

### 3. Convert the ML Model to C Array
- Train the model using `motion_model.py`
- Convert the `.tflite` file to a C array using:
  ```sh
  xxd -i motion_model.tflite > motion_model_data.h
  ```
- Include `motion_model_data.h` in the ESP32 project

### 4. Run the Project
- Open **Serial Monitor** (Baud rate: 115200)
- Move the sensor and observe real-time predictions

## Usage
Once running, the ESP32 will:
1. Read **MPU6050** sensor data (Acceleration & Gyroscope)
2. Preprocess and normalize the data
3. Pass the data through the **TFLite model**
4. Print the **predicted motion type** (e.g., `Forward`, `Spin`)

## Future Improvements
- Add more motion types (e.g., Jump, Walk, Stop)
- Improve accuracy with more training data
- Integrate with a mobile app for live monitoring

## License
This project is open-source under the **MIT License**.

## Contact
For questions or contributions, reach out at **your-email@example.com**.


