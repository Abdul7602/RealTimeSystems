# 🔐 ESP32-S3 FreeRTOS Mutex Example

A simple demonstration of using **FreeRTOS mutexes** on the **ESP32-S3** to safely share data between multiple tasks.  
This project runs entirely in **Wokwi**, using only the Serial Monitor — no extra hardware required. 🚀

---

## 🧠 Overview

This example shows how multiple FreeRTOS tasks can safely work with a shared variable:

- Two increment tasks update a shared counter.
- A serial input task lets you set the counter's starting value.
- A mutex ensures only one task accesses the counter at a time.

---

## ✨ Concepts Covered

- **Shared resource protection**  
- **Basic task scheduling in FreeRTOS**  
- **Mutex synchronization (`xSemaphoreTake` / `xSemaphoreGive`)**

---

## 🛠 Requirements

- **Board:** ESP32-S3 DevKitC-1  
- **Simulator:** Wokwi  
- **Framework:** Arduino (includes FreeRTOS)  
- **Hardware:** None — Serial Monitor only

---

## ▶ How to Run

1. Open Wokwi and create a new **ESP32-S3 Arduino** project.  
2. Paste the contents of `main.ino`.  
3. Click **Run**.  
4. Open the Serial Monitor (115200 baud).  
5. Enter a number (e.g., `50`) and press Enter.  
6. Watch the counter increase in a thread-safe way. 🧮

---
