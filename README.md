# Lakshmi-narayanan
Project for an embedded intern role
# ProblemStatemet1

This folder contains the FreeRTOS implementation for Problem Statement 1.

Files:
- main.c : Example code implementing ExampleTask1 and ExampleTask2 and Queue1.

Behavior:
- Queue1 created with depth 5 and elements of type Data_t.
- ExampleTask1 sends a Data_t built from global variables G_DataID and G_DataValue every 500 ms using vTaskDelayUntil for precise timing.
- ExampleTask2 blocks on the queue and processes messages according to the assignment rules:
  - dataID == 0 : delete ExampleTask2
  - dataID == 1 : process DataValue:
      - DataValue == 0 : increase ExampleTask2 priority by 2
      - DataValue == 1 : decrease priority back to original (if previously increased)
      - DataValue == 2 : delete ExampleTask2
- A SimulatorTask_UpdateGlobals is included to demonstrate runtime changes to G_DataID/G_DataValue. Remove this task if your system updates the globals elsewhere.

Build & Run:
- This code relies on your platform's FreeRTOS port and C runtime (printf retarget).
- Add to your project, ensure FreeRTOS config and hardware init (UART) present.
- Push this directory to the repository path:
  ProblemStatemet1/main.c
  ProblemStatemet1/readme.md

  # ProblemStatement2

  This project is a reference / evaluation PCB using the Nordic nPM1100 Power Management IC.
It converts 5V input to a regulated 3.0V output and also charges a Li-ion battery at about 200mA.

The design follows the assignment rules:

PCB Size: ≤ 35mm × 35mm

Maximum 4 layers

Only 0805-sized components used (easy for beginners to solder)

All SMD components are top-mounted

Input: 5V / 1A via 2-pin JST connector

Output: 3.0V regulated

LEDs show Power ON and Charging status

Bonus: Battery voltage measurement circuit connected to MCU ADC
