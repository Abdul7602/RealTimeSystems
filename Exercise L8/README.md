This project demonstrates deadlock conditions in FreeRTOS running on an ESP32, and shows three practical methods to resolve them:

    Timeout-based mutex acquisition
    Mutex hierarchy (consistent locking order)
    Arbitrator (global mutex control)

🧩 Author

Abdul Project for FreeRTOS learning on ESP32
🚀 Overview

In multitasking systems, deadlock occurs when two or more tasks are waiting indefinitely for each other to release resources.

This example uses:

    Two FreeRTOS tasks (Task A and Task B)
    Two mutexes (mutex_1, mutex_2)
    Optional global mutex (arbitrator)

Each task tries to take both mutexes, but in different orders — causing a deadlock scenario.

The program demonstrates three resolution strategies by defining a mode at the top of the code.
⚙️ Hardware & Software Requirements
🧩 Hardware

    ESP32 or ESP32-S3 development board
    USB cable for flashing and serial monitoring

💻 Software

    Arduino IDE (v2.x recommended)
    ESP32 Board Support Package
    FreeRTOS (included in ESP32 SDK)
    Serial Monitor (115200 baud)

🧪 Deadlock Example

In the original version, the following happens:

    Task A locks mutex_1, then waits for mutex_2.
    Task B locks mutex_2, then waits for mutex_1.
    Both tasks wait forever → deadlock!

// Task A
xSemaphoreTake(mutex_1, portMAX_DELAY);
vTaskDelay(1);
xSemaphoreTake(mutex_2, portMAX_DELAY);

// Task B
xSemaphoreTake(mutex_2, portMAX_DELAY);
vTaskDelay(1);
xSemaphoreTake(mutex_1, portMAX_DELAY);
