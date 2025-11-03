ESP32 Timer + Semaphore Rolling Average (Arduino-ESP32 v3.x)

This project demonstrates how to use esp_timer and a FreeRTOS binary semaphore to synchronize ADC sampling and task processing on an ESP32.
A hardware timer reads the analog input once per second and signals a task. The task maintains and prints a rolling average of the last five readings.

✅ Features

Uses esp_timer (Arduino-ESP32 3.x API) for periodic callbacks

Timer callback reads ADC values directly

A FreeRTOS binary semaphore safely signals the processing task

Task computes a 5-sample rolling average and prints it every second

Demonstrates interrupt-safe synchronization between ISR and FreeRTOS tasks

✅ Requirements

Arduino IDE 2.x (or PlatformIO)

ESP32 Arduino Core 3.x or newer

Any ESP32 development board

Analog input connected to the configured ADC pin (default: A0)

🧭 How to Use
Clone the Project
