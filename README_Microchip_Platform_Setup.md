# Microchip Platform Setup for ArrowML

## Overview

This project provides a sample setup for developing and testing applications on a Microchip platform as part of the ArrowML monorepo.

The initial objective is to:

* Set up a supported Microchip development environment.
* Verify that the evaluation board boots successfully.
* Verify RTOS support.
* Run a basic application example.
* Run a data processing example.
* Document the complete setup process.

This work serves as the foundation for the Azkoyen coffee machine project.

---

# Project Background

The long-term goal of this project is to monitor coffee machine operation **without installing additional sensors inside the machine**.

Instead, the system analyzes the electrical characteristics of the machine's power line (non-intrusive load monitoring).

Machine-learning models will later use the collected data to estimate parameters such as:

* Grinder power consumption
* Grinding duration
* Coffee particle size estimation
* Estimated amount of ground coffee
* Machine operating states

The embedded Microchip platform is responsible for collecting and transmitting this data for analysis.

---

# Hardware

Development Board:

* PIC32CXMTC-DB Evaluation Kit (EV58E84A)

The development board contains:

* PIC32CX microcontroller
* USB programming/debug interface
* Serial communication interface
* Power circuitry
* Peripheral interfaces

---

# Software Requirements

Install the following components.

## 1. MPLAB X IDE

Install the latest version of MPLAB X IDE.

Purpose:

* Project creation
* Source code editing
* Debugging
* Flashing firmware
* Serial terminal integration

---

## 2. MPLAB XC32 Compiler

The compiler converts C/C++ source code into executable firmware for the PIC32CX MCU.

Without the compiler, the IDE cannot build applications.

Compiler used:

* MPLAB XC32 Compiler

---

## 3. MPLAB Harmony 3

Harmony provides:

* Drivers
* Middleware
* BSP (Board Support Package)
* RTOS integration
* Example applications

Harmony is not an IDE and not a compiler.

---

# Connecting the Development Board

1. Connect the PIC32CXMTC-DB board to the PC using USB.
2. Verify that the operating system detects the USB device.
3. If required, install any USB drivers provided by Microchip.
4. Open MPLAB X IDE.
5. Select the connected debugger/programmer.
6. Open or create a project targeting the PIC32CX MCU.

---

# Building the Example

1. Open an example project.
2. Select:

* Correct device
* XC32 compiler
* Debug tool

3. Build the project.

Expected result:

```
Build Successful
```

---

# Flashing the Board

Flash the compiled firmware onto the board.

Expected result:

```
Programming...
Programming complete.
```

---

# Boot Verification

After programming:

* Reset the board.
* Open the serial terminal.

Expected result:

A boot message or command prompt appears.

Example:

```
Booting...

Microchip RTOS Demo

>
```

This satisfies the requirement:

> Microchip platform is booting to a serial prompt.

---

# Verifying RTOS Support

Check whether the platform supports an RTOS.

Examples include:

* FreeRTOS
* ThreadX (if supported)
* Bare-metal operation

Record:

* RTOS used
* Version
* Example executed successfully

---

# Running a Data Processing Example

Run one of the available Harmony example applications that performs data acquisition or processing.

Possible examples include:

* ADC sampling
* Signal processing
* DMA transfer
* FFT processing
* Sensor data collection

Verify:

* Application builds successfully.
* Firmware flashes successfully.
* Expected output appears on the serial terminal.

---

# Project Context

This setup will later be extended for the Azkoyen coffee machine project.

The Microchip platform will collect electrical characteristics from the power line.

ArrowML will then use these measurements to train machine-learning models capable of detecting:

* Grinding time
* Grinder power
* Coffee particle size
* Coffee quantity
* Machine operating states

No intrusive sensors will be installed inside the coffee machine.

---

# Acceptance Criteria

* [ ] Install Microchip development environment
* [ ] Verify RTOS support
* [ ] Board boots to a serial prompt
* [ ] README documents setup procedure
* [ ] Run a basic example
* [ ] Run a data processing example

---

# Notes

## IDE

MPLAB X IDE provides:

* Code editing
* Debugging
* Programming
* Project management

## Compiler

XC32 compiler converts source code into firmware executable by the PIC32CX MCU.

## Harmony

Harmony provides:

* Drivers
* Middleware
* BSP
* RTOS support
* Example projects

# Future Work

Future work includes:

* Collecting power-line measurements.
* Streaming data to ArrowML.
* Training machine-learning models.
* Performing real-time inference on coffee machine operating parameters.
