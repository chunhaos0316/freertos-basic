
This branch is used to run the FreeRTOS basic shell template on STM32F407G-DISC1.

We adapted TheKK/myFreeRTOS.

The source code of FreeRTOS kernel is in `freertos/FreeRTOS`.

Application code is in `source/main.c` and `source/lib`.

The build targets STM32F407VGT6 with:

- `STM32F40_41xxx`
- 168 MHz system clock from 8 MHz HSE
- 1 MB flash
- 128 KB SRAM plus 64 KB CCMRAM
- USART2 on PA2/PA3 at 115200 baud for the shell

The STM32F429I-Discovery LCD/SDRAM board support code is kept in the tree but is not used by this target.


## Flash
1. Download the source code: `git clone git@github.com:Justinsanity/freertos-basic`
2. Get into the project: `cd freertos-basic`
3. Make sure `arm-none-eabi-gcc`, `arm-none-eabi-ld`, `arm-none-eabi-objcopy`, Arm newlib, and `st-flash` are installed.
4. Compile: `make`
5. Flash: `make flash`

For the shell, connect an external USB-UART adapter:

- PA2: USART2 TX
- PA3: USART2 RX
- GND: common ground
- Baud rate: 115200 8N1
