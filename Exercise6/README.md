# FreeRTOS Binary Semaphore Demo (ESP32 / Wokwi)

This project demonstrates how to safely pass a **stack-based argument** to a FreeRTOS task using a **binary semaphore**.  
It meets the requirements of Exercise L-6 in the RTOS course.

---

## ✅ Key Points Matching the Moodle Assignment

### Binary Semaphore Usage
- Uses `xSemaphoreCreateBinary()`.  
- Parent task (`setup()`) waits with `xSemaphoreTake()` until the child task confirms it copied the stack variable.

### Stack-Based Argument
- The delay value (`delay_arg`) is a local variable in `setup()`.  
- Passed as `(void *)&delay_arg` to the `blinkLED` task.  
- The task copies it immediately to its own local variable to avoid invalid memory access.

### Task Synchronization
- `blinkLED` calls `xSemaphoreGive(bin_sem)` right after copying the argument.  
- `setup()` waits with `xSemaphoreTake(bin_sem, portMAX_DELAY)` before printing `"Done!"`.

### Functional Requirements
- Reads an integer from the Serial Monitor.  
- Passes it safely to a FreeRTOS task.  
- LED blinks with the entered delay.  
- Serial output confirms the value received.

### Wokwi Compatibility
- Fully works on the **ESP32 simulator** with serial input.

---

## 🔹 Conclusion

This implementation matches exactly what the Moodle L-6 assignment requires:

- Binary semaphore ✅  
- Stack-based argument passing ✅  
- Task synchronization ✅  
- Wokwi-ready ✅
