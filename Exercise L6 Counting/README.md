FreeRTOS Counting Semaphore Demo (ESP32)

This project provides a hands-on introduction to FreeRTOS counting semaphores using an ESP32. It is divided into two main demonstrations.

🔹 Part 1 — Five Tasks Synchronizing With a Counting Semaphore

Five worker tasks are created, all receiving the same Message structure from the creator task.

To ensure safe parameter transfer:

A counting semaphore (max count = 5, initial count = 0) acts as a barrier.

Each task copies the stack-allocated message into its own local buffer.

After copying, the task gives the semaphore.

The creator task waits for 5 semaphore signals before proceeding.

This guarantees that the main task does not overwrite the message before all tasks have safely copied it.

🔹 Part 2 — Creating One Task Per Word in a User Sentence

In the second demonstration, the program waits for the user to enter a sentence over the serial interface.

Workflow

The input sentence is split into words.

One task is created for each word.

Each word-task does the following:

Receives a heap-allocated Message* containing its word.

Copies the data into a local variable.

Frees the original pointer to avoid memory leaks.

Signals a counting semaphore to confirm it has received the parameter.

Prints the assigned word.

Deletes itself.

This demonstrates safe dynamic task creation and safe parameter passing using heap memory.

If you'd like, I can wrap this into a full README.md file with headers, code blocks, usage instructions, and example output.
