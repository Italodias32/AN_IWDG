# AN_IWDG

This is an application note about IWDG for STM32 using STM32F103RB and developed in STMCubeIDE1.3.0. Available in: [AN_IWDG](https://github.com/Italodias32/AN_IWDG/files/6098790/AN_IWDG.pdf)

Developed by Italo Dias and Sarah Oliveira

## Introduction

This program was developed as a work in the discipline of Embedded Systems Programming at UFMG - Prof. Ricardo de Oliveira Duarte - Department of Electronic Engineering. The program was developed and tested with STM32F103RB and developed in STMCubeIDE1.3.0. 
The example presented is located in the “Core / Src / main.c” directory and proposes to publicly present, in a didactic way, the usefulness of the Independent Watchdog peripheral (IWDG) through an application example. 
The example implemented with the Independent Watchdog peripheral explores two of its features: the restart of the microcontroller and its internal clock. The example can be observed visually, with the activation of one of the LED for a certain time, which can be configured by the values “counter clock prescaler” and “down-counter reload value”. These data consist, respectively, of the clock frequency division value and the counter reload value (which will count downwards), together to define the clock timeout period. These data are inserted in the STM32CubeIDE1.3.0 interface, in the “.ioc” area.
In the sequence, the implemented code initializes the dynamics with the writing of "0xAAAA" in the Key Register to reload the counter, and with the writing of "0xCCCC" in the Key Register to promote initialization. This procedure is identified and preceded by turning on the first LED.
Then, the dynamics of turning on / off a second LED in an infinite loop is implemented. Thus, when it is identified that the button has been pressed, the second LED lights up and remains on for 1 second. Then the two LEDs are extinguished and the watchdog counter is reloaded by writing “0xAAAA” in the Key Register. Finally, after half a second, the code resets.

<div align="center"><img src="https://user-images.githubusercontent.com/38631264/110269719-0e39d500-7fa3-11eb-96c4-645d102a3dfe.gif" width="700"></div>

## Peripheral presentation

The Independent Watchdog (IWDG) consists of a peripheral designed for the surveillance of embedded systems, aiming at security, time control and flexibility of use. It acts when a software failure occurs, in order to detect and resolve a malfunction and then trigger the system reset, when the time counter reaches a limit value.
Although crashes in the execution of an application in microcontrollers occur rarely, the existence of the Watchdog is important to act in these situations. Some cases in which this can happen are when there is no forecast of any use during the design of an application; when some resource is not used correctly or when there is a hardware failure, due to external conditions or due to the conditions of use of the device.

## Steps Performed

1. Hardware configuration: clock timeout period.
2. Activation of the 1st LED.
3. Recharge the watchdog counter.
4. Initialization of the Independent Watchdog.
5. Test whether the button has been pressed.
6. If yes, also activate the 2nd LED for 1s.
7. Turn off the two LEDs.
8. Recharge the watchdog counter.
9. Waits for 5s.
10. Resetting the code / Return to step 2.

## References
[1.] Slides provided by the teacher: Lesson 12.

[2.] ST Microelectronics. RM0008 (Reference manual). STM32F101xx, STM32F102xx, STM32F103xx, STM32F105xx and STM32F107xx advanced ARM®-based 32-bit MCUs.

[3.] [STM32WB - IWDG](https://www.st.com/content/ccc/resource/training/technical/product_training/group0/01/24/22/29/38/70/40/57/STM32WB-WDG_TIMERS-Independent-Watchdog-IWDG/files/STM32WB-WDG_TIMERS-Independent-Watchdog-IWDG.pdf/jcr:content/translations/en.STM32WB-WDG_TIMERS-Independent-Watchdog-IWDG.pdf) - More about IWDG
