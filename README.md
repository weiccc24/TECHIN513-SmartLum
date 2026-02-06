# SmartLum: Circadian-Adaptive IoT Lighting System 💡

> **TECHIN 513 - Signal Processing & Machine Learning (University of Washington)** > *An intelligent lighting solution that optimizes indoor illumination for circadian health using environmental signal processing and machine learning.*

## 📌 Project Overview
People living in northern latitudes often experience limited natural sunlight, leading to disrupted circadian rhythms and reduced productivity. **SmartLum** is an IoT-enabled adaptive lighting system that bridges the gap between static artificial lighting and natural solar cycles.

Unlike standard "smart bulbs" that rely on rigid schedules, SmartLum uses **Signal Processing** to filter noisy environmental data and a **Machine Learning** regression model to predict the optimal brightness and color temperature for the user in real-time.

## ✨ Key Features
* **Environmental Sensing:** Real-time acquisition of ambient light (Lux) and color temperature (Kelvin) using the TCS34725 sensor.
* **Signal Processing:** Implementation of **Moving Average Filters** and **IIR Filters** to smooth sensor noise and prevent light flickering.
* **Machine Learning Integration:** Uses a **Linear Regression** model trained on circadian health data to predict ideal lighting conditions.
* **Automatic Adaptation:** Dynamically adjusts the LED strip's warmth (2700K-6500K) and brightness based on the time of day and current room conditions.

## 🛠️ Tech Stack
* **Hardware:** ESP32 Microcontroller, TCS34725 RGB Sensor, NeoPixel LED Ring (WS2812B).
* **Firmware:** C++ / Arduino Framework.
* **Machine Learning:** Python, Scikit-Learn, Pandas (for synthetic data generation and training).
* **Data Processing:** NumPy, Matplotlib.

## 📂 Repository Structure
```text
TECHIN513-SmartLum/
├── firmware/           # ESP32 C++ code for sensor reading & LED control
│   └── main.ino
├── ml_model/           # Python scripts for data generation & model training
│   ├── synthetic_data_gen.py   # Generates training dataset based on circadian logic
│   ├── train_model.py          # Trains the regression model
│   └── dataset.csv             # Synthetic training data
├── docs/               # Project documentation & schematics
└── README.md           # Project documentation
```
## 🚀 How It Works
**1.** Sensing: The TCS34725 reads the current ambient light.

**2.** Filtering: The ESP32 applies a low-pass filter to remove transient noise (e.g., shadows from passing objects).

**3.** Inference: The system inputs the filtered data + current time into the ML model (deployed on-device) to calculate the target Brightness and Kelvin.

**4.** Actuation: The NeoPixels update smoothly to the new target state.

## 📊 System Architecture
(A screenshot of our block diagram or circuit will be added here)

## 👥 Team
**Wei-Ling Chang** - M.S. Technology Innovation, University of Washington

**Proud Dumrongpun** - M.S. Technology Innovation, University of Washington

Created for TECHIN 513 at the Global Innovation Exchange (GIX), University of Washington.
