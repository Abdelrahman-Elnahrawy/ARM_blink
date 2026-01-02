# ARM_Blink 🚀
**EG_FWD Advanced Embedded Systems Track - Project 01**

![Architecture](https://img.shields.io/badge/Architecture-ARM_Cortex--M4-blue?style=for-the-badge&logo=arm)
![Language](https://img.shields.io/badge/Language-Embedded_C-red?style=for-the-badge&logo=c)
![Platform](https://img.shields.io/badge/Platform-STM32-00356A?style=for-the-badge&logo=stmicroelectronics)

This repository contains the first project of the **EG_FWD Advanced Embedded Systems Track**. It demonstrates fundamental low-level programming on ARM-based microcontrollers, focusing on Peripheral Clock control and GPIO manipulation via direct register access.

---

## 🎯 Project Objective
The goal of this project is to implement a robust LED blinking application without using high-level abstraction layers (like HAL or Arduino). Instead, it focuses on:
* **RCC (Reset and Clock Control):** Enabling the peripheral clock for the target GPIO Port.
* **GPIO Configuration:** Setting pin modes (Output), output types (Push-Pull), and speed via memory-mapped registers.
* **Bit Masking:** Utilizing bitwise operators (`&`, `|`, `^`, `<<`) to modify specific register bits without affecting others.

---

## 🛠 Hardware & Tools
* **Microcontroller:** ARM Cortex-M4 (STM32F4 Series)
* **Debugger/Programmer:** ST-LINK V2
* **Development Environment:** STM32CubeIDE / Keil uVision
* **Toolchain:** GNU Arm Embedded Toolchain (GCC)

---

## 💻 Register-Level Implementation
The project avoids library calls and directly interacts with the processor's memory map.

### 1. Clock Enablement
Before a peripheral can be used, its clock must be enabled in the `RCC_AHB1ENR` register. 


### 2. GPIO Configuration
* **MODER:** Configured for General Purpose Output Mode.
* **ODR:** Toggled within a software delay loop to create the blinking effect.

---

## 📂 Project Structure
```text
/ARM_blink
  ├── /Inc
  │    └── stm32f4xx.h      # Device-specific register definitions
  ├── /Src
  │    └── main.c           # Core logic and register manipulation
  ├── Startup.s             # Assembly startup code & Vector Table
  └── README.md
