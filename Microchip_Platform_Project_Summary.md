# Microchip Platform Setup Project Summary

## Project Goal

Prepare a sample setup for a Microchip platform in the ArrowML monorepo.

The objective is **not** to build a complete firmware application from
scratch. Instead, the goal is to demonstrate that a Microchip platform
can be integrated into ArrowML by setting up the development
environment, running vendor examples, verifying RTOS support, and
documenting the process.

## Deliverables

### 1. Investigate the development environment

Determine:

-   Which IDE Microchip officially supports
    -   MPLAB X IDE
    -   VS Code (MPLAB extension)
-   Which workflow is recommended
-   Which compiler is required
    -   XC8
    -   XC16
    -   XC32

One project objective is to prefer VS Code whenever possible, so verify
whether Microchip officially supports development using VS Code.

### 2. Set up the development environment

Install:

-   VS Code + MPLAB extension or
-   MPLAB X IDE

Install the compiler matching the selected MCU.

Examples:

-   PIC18 → XC8
-   dsPIC → XC16
-   PIC32 / SAM → XC32

### 3. Select a supported development board

Choose a Microchip development board, for example:

-   Curiosity Nano
-   PIC32 Curiosity
-   SAM E54 Xplained Pro
-   Explorer board

The development board determines:

-   MCU family
-   Compiler
-   Supported examples

### 4. Connect the board

Connect the board via USB for:

-   Programming (flashing)
-   Debugging
-   Serial communication

### 5. Run a basic example

Examples include:

-   Blink LED
-   UART
-   Timer
-   Hello World over serial

Acceptance criteria require verifying that the platform boots to a
serial prompt.

### 6. Verify RTOS support

Check whether the selected platform supports RTOSes such as:

-   FreeRTOS
-   Azure RTOS
-   Micrium
-   ThreadX (if applicable)

### 7. Run a data processing example

Run an example that performs some computation, such as:

-   Sensor processing
-   ADC processing
-   Filtering
-   Averaging
-   Serial data parsing
-   Powerline data processing (if available)

### 8. Add everything to ArrowML

Include:

-   Example code
-   Project files
-   Configuration
-   README

### 9. Write a README

Document:

-   Hardware used
-   IDE
-   Compiler
-   Drivers
-   Build steps
-   Flash steps
-   Serial connection
-   Running the example
-   Expected output

## Acceptance Criteria

  Requirement                       Verification
  --------------------------------- ------------------------------------
  Verify RTOS support               Identify supported RTOSes
  Platform boots to serial prompt   Flash board and verify UART output
  README added                      Document complete setup
  Run data processing example       Execute a working example

## Workflow

1.  Choose a supported development board.
2.  Install IDE.
3.  Install compiler.
4.  Install required drivers.
5.  Open an example project.
6.  Build (compile).
7.  Flash the MCU.
8.  Connect to the serial terminal.
9.  Verify boot prompt.
10. Run a data processing example.
11. Add documentation and commit to ArrowML.

## Open Question

The remaining question is **which development board (and MCU family)**
should be targeted. This determines:

-   Compiler
-   Example projects
-   RTOS support
-   Toolchain
