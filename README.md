# Thermostat Prototype Project

## Project Summary

In this project, I designed and implemented a smart thermostat prototype to manage heating and cooling in response to ambient temperature readings. Using a Raspberry Pi, an AHT20 temperature sensor (via I²C), and two PWM-controlled LEDs, the system cycles through Off, Heat, and Cool states based on a finite state machine (FSM). Three buttons allow users to toggle modes and adjust the set point, while an LCD displays the date, time, current temperature, and system state. Finally, the thermostat outputs status updates over UART every 30 seconds. This prototype addresses SysTec’s need for a low-level thermostat prototype before cloud integration. 

![ThermostatSet](https://github.com/user-attachments/assets/476dd942-58d1-46f3-aed8-fa3378719171)    ![ThermostatSet2](https://github.com/user-attachments/assets/684dfdb6-b097-4c9c-bade-6a2af41b161f)

## What Went Well 


I successfully implemented a robust three-state FSM using the `statemachine` library, accurately documented transitions, and validated functionality with the `MultiButtonTest.py` script. Integrating multiple peripherals—buttons (GPIOZero), LEDs, I²C sensor, LCD, and UART—reinforced my hardware interfacing skills and ensured reliable prototype behavior. citeturn0file1

## Areas for Improvement

While the prototype functions correctly, I can improve by adding hardware debouncing for button inputs, implementing fault detection (e.g., sensor read failures), and optimizing threading to avoid potential race conditions in display updates and serial transmissions.

## Tools & Resources Added

- **gpiozero** and **Adafruit CircuitPython AHTx0** libraries for sensor integration
- **statemachine** Python package for clean FSM implementation
- **draw.io** for state machine diagrams citeturn0file2
- Official datasheets and documentation from Raspberry Pi Foundation, Microchip, and NXP

## Transferable Skills

- Designing and implementing FSMs for embedded control
- Hardware interfacing with I²C, PWM, GPIO, and UART protocols
- Threading and concurrency for managing display updates and serial I/O
- Writing clear, maintainable Python code with comprehensive documentation

## Maintainability, Readability & Adaptability

To ensure maintainability, I encapsulated display logic in the `ManagedDisplay` class, used descriptive function and variable names, and centralized configuration values (e.g., GPIO pins, set point). Inline comments, change logs, and debug flags aid readability, while the modular state machine design allows easy extension to adaptive modes or cloud connectivity.
