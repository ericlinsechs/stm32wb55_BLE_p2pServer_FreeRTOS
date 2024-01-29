# stm32wb55_BLE_p2pServer_FreeRTOS

## Overview
This repository contains an example of replacing the original ST sequencer scheduler with FreeRTOS in a Bluetooth Low Energy (BLE) Peer-to-Peer (P2P) server project on the STM32WB55 microcontroller.

## Architecture
- FreeRTOS

## Requirements
- STM32CubeIDE
- STM32WB55 Nucleo board or similar development board
- android/ios device with the ST BLE Sensor application

## Configuration
This application requires having the stm32wb5x_BLE_Stack_full_fw.bin binary flashed on the Wireless Coprocessor.
If it is not the case, you need to use STM32CubeProgrammer to load the appropriate binary.
All available binaries are located under /Projects/STM32_Copro_Wireless_Binaries directory.
Refer to /Projects/STM32_Copro_Wireless_Binaries/ReleaseNote.html for the detailed procedure to change the Wireless Coprocessor binary.

## Usage
1. Import this repository into STM32CubeIDE
2. Build the project
3. Run the project
4. On the android/ios device, enable the Bluetooth communications, and if not done before,
    - Install the ST BLE Sensor application on the ios/android device
    https://wiki.st.com/stm32mcu/wiki/Connectivity:BLE_smartphone_applications#ST_BLE_Sensor
    - Power on the Nucleo board with the BLE_P2P_Server application
    - Then, click on the App icon, ST BLE Sensor (smartphone)
    - Connect to the device
    - Select the P2PSRVx in the device list and play with the Light and the SW1 button of the board

## Debug

To enable the debugger, modify the `Core/Inc/app_conf.h` file:

```c
#define CFG_DEBUG_TRACE_FULL    1
#define CFG_DEBUGGER_SUPPORTED  1 
#define CFG_DEBUG_BLE_TRACE     1
#define CFG_DEBUG_APP_TRACE     1
```

