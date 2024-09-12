# 11310PME 520300 Digital Control System Lab

The Digital Control System Lab aims to provide a basic understanding and hands-on exercises in digital control systems. First, we will introduce the STM32, a popular microcontroller on the market. Finally, we will implement a simple position control of a DC motor using the STM32. The labs will cover the following topics:

1. Using STM32 through STM32CubeIDE
2. System identification of a DC motor
3. Digital controller design
4. Control performance evaluation


# Lab 1
**Due: 2024/10/11**
## Prerequisites
1. Create a ST account and install STM32CubeIDE. [link](https://www.st.com/en/development-tools/stm32cubeide.html#st-get-software)
2. Download Serial Oscilloscope. [link](https://x-io.co.uk/serial-oscilloscope/?fbclid=IwAR13yfXLrlEqIN43_gwaLuXaDHyjBJ4A-tjQ7xC2OXT-ltaDHCbIN7h_T-Y)
3. Download `Lab1.zip`, import into STM32CubeIDE, and run the sample code.
   * open STM32CubeIDE and **login** with your ST account
     * *if can't login, try [this](https://blog.csdn.net/ken2232/article/details/132644795)*
   * import the project
      ```
      open STM32CubeIDE -> import -> general -> existing projects into workspace -> select archive file -> browse -> select Lab1.zip -> finish
      ```
   * run the project
     1. connect the STM32F446RE board to the computer
     2. open `main.c` at `Core/Src/main.c`
     3. click the *hammer* icon on the top bar to build the project
     4. click the *play* icon to run the project or \
        click the *bug* icon to debug mode -> click the *play* icon to run the project \
          * *update ST_link if needed*
     6. open the serial oscilloscope
     7. You should see "i love controller system" printing out every 1 second


https://github.com/user-attachments/assets/0818975b-82bf-46a2-b01d-9f0bbfe40b64





## ! Requirements !
1. Properly solder PCB pins.
2. Blink the `LED2(PA5)` on the STM32F446RE board in 2Hz.
3. Use the `user button(PC13)` to switch between on/off of the LED2.
   
   *See STM32F446RE user manual section 6.4, 6.5 for pins definition*
5. Print out how many times the LED2 has blinked on the serial oscilloscope.
   ```shell
   // example output
   LED has blinked 1 time(s)
   LED has blinked 2 time(s)
   ......
   ```

*Tips*
```c
void HAL_GPIO_ReadPin (GPIO_TypeDef * GPIOx, uint16_t GPIO_Pin)
void HAL_GPIO_WritePin (GPIO_TypeDef * GPIOx, uint16_t GPIO_Pin, GPIO_PinState PinState)
void HAL_GPIO_TogglePin (GPIO_TypeDef * GPIOx, uint16_t GPIO_Pin)
void HAL_Delay (uint32_t Delay)
```

## Supplementary Resources
To learn more about STM32...

* [! Push Button with STM32 Nucleo using STM32CubeIDE](https://microcontrollerslab.com/push-button-with-stm32-nucleo-stm32cubeide/)

* [! Youtube - ControllerTech](https://www.youtube.com/@ControllersTech/playlists)

* [Datasheet - STM32F446](https://www.st.com/resource/en/datasheet/stm32f446re.pdf)

* [User Manual - STM32F446RE](https://www.st.com/resource/en/user_manual/um1724-stm32-nucleo64-boards-mb1136-stmicroelectronics.pdf)

* [HAL Library for STM32F4](https://www.st.com/resource/en/user_manual/um1725-description-of-stm32f4-hal-and-lowlayer-drivers-stmicroelectronics.pdf)
