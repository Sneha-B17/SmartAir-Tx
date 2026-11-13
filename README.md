# SmartAir - Temperature and Humidity Monitoring

## Overview
SmartAir is an RTOS-based temperature and humidity monitoring project developed using the STM32F429ZIT6 Discovery Board and DHT11 sensor. The system periodically acquires temperature and humidity readings and displays the collected data through UART on Tera Term.

## Hardware Requirements
- STM32F429ZIT6 Discovery Board
- DHT11 Temperature and Humidity Sensor
- UART connection for serial monitoring

## Software Requirements
- Embedded C
- STM32CubeIDE
- FreeRTOS
- STM32 HAL Library
- Tera Term

## Features
- Temperature and humidity data acquisition using DHT11
- Periodic sensor reading using FreeRTOS software timers
- Inter-task data communication using queues
- Binary semaphore for synchronization
- Mutex for protecting shared UART output
- UART-based real-time monitoring on Tera Term
- GPIO external interrupt-based synchronization

## RTOS Task Architecture

**Send Task**
- Reads temperature and humidity from the DHT11 sensor.
- Sends the readings to a FreeRTOS queue.

**Receive Task**
- Receives temperature and humidity values from the queue.
- Displays the readings through UART using `printf()`.

## Synchronization and Communication
- **Queue:** Transfers temperature and humidity data between tasks.
- **Binary Semaphore:** Controls synchronization of sensor data acquisition.
- **Mutex:** Protects shared UART output and prevents concurrent access.
- **Software Timers:** Generates periodic events for sensor acquisition and status reporting.
- **External Interrupt:** Releases the binary semaphore through an ISR callback.

## UART Output
Temperature and humidity readings are displayed on Tera Term.

Example:
```text
Temp->28 Hum->65
```

## Concepts Used
- STM32 Microcontroller Programming
- Embedded C
- FreeRTOS Multitasking
- Task Synchronization
- Queues
- Binary Semaphores
- Mutexes
- Software Timers
- GPIO External Interrupts
- UART Communication
- DHT11 Sensor Interfacing

## Author
Sneha B.
