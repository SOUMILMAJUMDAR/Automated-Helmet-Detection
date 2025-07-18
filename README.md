



Automated Helmet Detection System

ESP32-CAM + Edge Impulse + U8g2 OLED Display

This project demonstrates an AI-powered helmet detection system using the **ESP32-CAM module**, integrated with **Edge Impulse** for real-time image classification and the **U8g2** library for displaying results on an OLED screen. Designed for low-power embedded applications, this solution detects whether a person is wearing a helmet, making it suitable for road safety enforcement and smart surveillance systems.



 Features

* Real-time image capture using the **ESP32-CAM (AI Thinker)**
* Image classification with a custom model trained via **Edge Impulse**
* OLED feedback using the **U8g2** graphics library (128x64 I2C display)
* Camera pin mapping for **AI Thinker** variant
* Serial logging for predictions and model inference timing
* Optimized for on-device AI inference



Hardware Requirements

* ESP32-CAM (AI Thinker variant)
* 128x64 OLED display (I2C)
* USB-to-Serial converter (for flashing and monitoring)
* 5V power source
* Jumper wires and breadboard



Software Stack

* Arduino Framework
* Edge Impulse Inference SDK
* ESP32 Camera driver
* U8g2 Graphics library
* C/C++ via Arduino IDE or PlatformIO



Camera Pin Configuration

For AI Thinker model:

```cpp
#define PWDN_GPIO_NUM     32
#define RESET_GPIO_NUM    -1
#define XCLK_GPIO_NUM      0
#define SIOD_GPIO_NUM     26
#define SIOC_GPIO_NUM     27
#define Y9_GPIO_NUM       35
#define Y8_GPIO_NUM       34
#define Y7_GPIO_NUM       39
#define Y6_GPIO_NUM       36
#define Y5_GPIO_NUM       21
#define Y4_GPIO_NUM       19
#define Y3_GPIO_NUM       18
#define Y2_GPIO_NUM        5
#define VSYNC_GPIO_NUM    25
#define HREF_GPIO_NUM     23
#define PCLK_GPIO_NUM     22
```

---

Functionality Overview

1. OLED Welcome Screen
   Displays introductory messages about the project group and purpose.

2. Camera Initialization
   Configures and initializes the ESP32-CAM with the specified pinout.

3. Continuous Inference Loop
   Captures an image, processes it, runs it through the Edge Impulse model, and displays results on the OLED.

4. Result Output
   Displays the prediction label and confidence percentage on the OLED. Logs full inference details to the serial monitor.

---

Folder Structure (Sample)

```
.
├── src/
│   ├── main.cpp
│   └── sxmnath-project-1_inferencing.h  # Edge Impulse model header
├── edge-impulse-sdk/
├── README.md
├── platformio.ini / .ino
```

---

Getting Started

1. Install Required Libraries

   * U8g2 (via Library Manager)
   * Edge Impulse Inference SDK (from Edge Impulse project)
   * ESP32 Board support (via Board Manager)

2. Train and Download Model

   * Train your custom image classification model in Edge Impulse.
   * Export as "Arduino Library" and include it in the project.

3. Upload Code

   * Use Arduino IDE or PlatformIO
   * Board: `AI Thinker ESP32-CAM`
   * Flash and open serial monitor at 115200 baud rate.

---

Example Output

Serial Output:

```
Predictions (DSP: 98 ms., Classification: 234 ms., Anomaly: 0 ms.)
  Helmet (0.95) [ x: 44, y: 21, width: 100, height: 120 ]
```

OLED Display:

```
Helmet - 95%
```

---

Notes

* Ensure the correct sensor type is selected in the Edge Impulse model (`EI_CLASSIFIER_SENSOR_CAMERA`).
* The OLED display uses software I2C on GPIO 14 (SCL) and GPIO 15 (SDA).
* Modify `camera_config` and display settings if using a different ESP32-CAM variant or screen.



Credits

* Edge Impulse - for providing the inference SDK
* U8g2 - OLED library by Oliver Kraus
* Espressif - for ESP32-CAM and camera driver


CIRCUIT DIAGRAM
<img width="710" height="614" alt="image" src="https://github.com/user-attachments/assets/b96c7d3a-f613-46b0-bdfb-d924d1844cee" />




