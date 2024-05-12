# MOTION DETECTION SYSTEM USING PIR SENSOR AND VSDSQUADRON MINI

## OVERVIEW
The project aims to create a motion detection system using a Passive Infrared (PIR) sensor and the VSDsquadron Mini Board. When motion is detected by the PIR sensor, the system activates an LED to indicate the presence of motion.
* Detection: The PIR sensor continuously monitors its surroundings for any movement. When it detects motion, it sends a signal to the VSDsquadron Mini Board.
* Processing: The VSDsquadron Mini Board receives the signal from the PIR sensor and processes it using its onboard microcontroller.
* LED Activation: Upon detecting motion, the microcontroller activates the LED connected to it, illuminating it to indicate the presence of motion.

## COMPONENTS
* PIR Sensor
* VSDSquadron Mini Board
* LED
* Jumper wire(Female to FEmale)
* VS Code for uploading the code in which PLATFORM IO installation should be there.

## HARDWARE CONNECTIONS

#### PIR CONNECTIONS
* Output Pin of PIR connected to PD2 Of VSDSquadron Mini Board.
* VCC Of PIR coonected to 5V Of VSDSquadron Mini Board.
* GND Pin of PIR connected to GND Of VSDSquadron Mini Board.

#### LED CONNECTION
* LED Anode Pin connected to PD6 Of VSDSquadron Mini Board.
* LED Cathode connected to GND Of VSDSquadron Mini Board.

## CODE FOR PROGRAMMING
```
#include <ch32v00x.h>
#include <debug.h>

#define BLINKY_GPIO_PORT GPIOD
#define BLINKY_GPIO_PIN GPIO_Pin_6
#define PIR_GPIO_PIN GPIO_Pin_2 // PIR sensor output connected to GPIO Pin 2
#define BLINKY_CLOCK_ENABLE RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOD, ENABLE)

void NMI_Handler(void) _attribute_((interrupt("WCH-Interrupt-fast")));
void HardFault_Handler(void) _attribute_((interrupt("WCH-Interrupt-fast")));
void Delay_Init(void);
void Delay_Ms(uint32_t n);

int main(void)
{
    NVIC_PriorityGroupConfig(NVIC_PriorityGroup_2);
    SystemCoreClockUpdate();
    Delay_Init();

    GPIO_InitTypeDef GPIO_InitStructure = {0};

    BLINKY_CLOCK_ENABLE;
    GPIO_InitStructure.GPIO_Pin = BLINKY_GPIO_PIN;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
    GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;
    GPIO_Init(BLINKY_GPIO_PORT, &GPIO_InitStructure);

    // Configure PIR sensor input pin
    GPIO_InitStructure.GPIO_Pin = PIR_GPIO_PIN;
    GPIO_InitStructure.GPIO_Mode = GPIO_Mode_IPU; // Input mode with pull-up
    GPIO_Init(GPIOD, &GPIO_InitStructure);

    while (1)
    {
        // Read PIR sensor status
        uint8_t pirStatus = GPIO_ReadInputDataBit(GPIOD, PIR_GPIO_PIN);

        // Control the LED based on PIR sensor output
        if (pirStatus == 1) // PIR sensor detected motion
        {
            GPIO_WriteBit(BLINKY_GPIO_PORT, BLINKY_GPIO_PIN, SET); // Turn on LED
        }
        else
        {
            GPIO_WriteBit(BLINKY_GPIO_PORT, BLINKY_GPIO_PIN, RESET); // Turn off LED
        }

        Delay_Ms(1000);
    }
}

void NMI_Handler(void) {}
void HardFault_Handler(void)
{
    while (1)
    {
    }
}
```

## APPLICATION VIDEO


https://github.com/Rajveer-1234/vsdsquadron_mini_intership/assets/110220051/1315dee6-93b1-4e53-9a32-b30ca2ebacae




