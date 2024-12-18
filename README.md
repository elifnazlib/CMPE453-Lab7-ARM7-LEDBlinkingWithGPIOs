# ARM7: GPIO and Led Blinking

Before starting to Lab
- Firstly, please open Proteus 8.17
- You will go to File --> Open Sample Project
- Write "led blink" to Keywords, then select the STM32F 102 Blink LED Project and open.

![image](https://github.com/user-attachments/assets/4c2c9949-c3d9-4cc5-bd38-68cfae6a62fe)

<br>

- You can open Schematic Capture and Source Code on the top.

![image](https://github.com/user-attachments/assets/7162e14a-561e-4fbc-bfcd-a17b11e3cef0)

<br>

- Firstly, please investigate the code then go to Debug --> Run Simulation. You will see the running circuit.

<br>

## QUESTIONS

1. Please add one led to PB6 for 1 second blink, and add the screenshot of the circuit.

**Answer:** 
<div align="center">
<img src="https://github.com/elifnazlib/CMPE453-Lab7-ARM7-LEDBlinkingWithGPIOs/blob/main/answer_for_q1.png" width="256">
</div>

2. What changes were made to add the new LED? Please write the code parts according to that and explain in detail.

**Answer:** To add LED to PB6 and have blink with 1 second delay, we should have the code: 
```c
while (1) 
{ 
    HAL_GPIO_TogglePin(Ld2_GPIO_Port, Ld2_Pin); //Toggle LED 
    HAL_Delay(1000); //Delay 1 Seconds 
} 
```
```Ld2_GPIO_Port``` should be Port B and Ld2_Pin should be Pin 6. (Assuming GPIO_PORT_B and PIN6 are defined appropriately, ```HAL_GPIO_TogglePin(GPIO_PORT_B, PIN6);```) 

3. What happens if the ```HAL_Delay(1000)``` value is modified? Give examples and explain. 

**Answer:** The delay between blinks will change to that ms. For example, if we use 
```HAL_Delay(3000)```, the LED will wait for 3 seconds before the next blink.

4. What does the ```HAL_GPIO_TogglePin``` function do? What parameters does it take?

**Answer:** It toggles the GPIO pin whose port is stated in the parameters. The function 
comes from the header file. It takes the parameters GPIOx and GPIO_Pin which are the 
port of the pin to be toggled and the pin number respectively.
