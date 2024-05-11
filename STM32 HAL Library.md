# STM32 HAL Library
STMCube® is STMicroelectronics’s original initiative to ease and accelerate the development cycle of embedded products. STM32Cube covers the STM32 portfolio of microcontrollers.
It provides the developer with all the low-level drivers, APIs, and enables him/her to dedicate most of the effort to develop the application layer and any required middleware.
# STM32 HAL Library Drivers
The STM32CubeMX, a graphical software configuration tool that allows generating C initialization code using graphical wizards.

The STM32Cube Hardware Abstraction Layer (HAL), an STM32 abstraction layer embedded software ensuring maximized portability across the STM32 microcontroller. The HAL is available for all the hardware peripherals.

The low-layer APIs (LL) offering a fast light-weight expert-oriented layer that is closer to the hardware than the HAL. The LL APIs are available only for a set of peripherals.

The HAL and LL are complementary and cover a wide range of applications requirements:

The HAL offers high-level and feature-oriented APIs, with a high-portability level. They hide the MCU and peripheral complexity to end-user.
The LL offers low-level APIs at registers level, with better optimization but less portability. They require deep knowledge of the MCU and peripherals specifications.
The source code of HAL and LL drivers is developed in Strict ANSI-C which makes it independent from the development tools. It is fully documented and is MISRA-C 2004 compliant.
# STM32 HAL Drivers Examples
You can find in "img" file
# HAL Detailed Function Description
In the same manner, there are low-level hardware drivers for almost all the hardware peripherals in the STM32 microcontrollers. Including Timers, ADC, USART, I2C, USB, DAC, Comparators, etc.
We’ll configure these peripherals and generate the initialization C-Code using the CubeMX software tool. Here is a screenshot for what it looks like inside the interface where we configure the timer module for example.
# Hardware Timer Module Configuration Within CubeMX
You can find in "img" file
# STM32 HAL Concluding Remarks
Using the STM32 HAL device drivers can be advantageous in so many situations, and help shorten the development time. Especially for projects that fall in the category of “proof of concept”. I think no one wants to spend so much time building a complete software stack for a specific target then it proves the main idea needs more refinement or the target itself does not perform well enough.

However, the moderately high-level APIs provided by the HAL may have extra more features than what you may actually need in some situations. So you end up using more memory space and executing some tasks a little bit slower due to the overhead of the functionalities embedded in the libraries.

You can use the LL drivers and optimize more at the register level in order to enhance memory utilization or the speed of execution. However, the application at the end would not be easily portable across multiple targets.

All in all, we’ll be using the STM32 CubeMX tool to generate HAL + LL drivers C-Code to initialize our hardware. Then we’ll be developing the application layer and some middleware stuff on the way.

STM32 Embedded Software Layered Architecture

Mostly, we’ll be focusing on the ECUAL layer building some firmware drivers, and testing them in different applications. Those drivers must be easily reconfigurable and completely portable.

To achieve reconfigurability, we’ll use something called “Linking Configuration” that you’ll learn in the next tutorials. And in order to achieve the portability requirement, the drivers will be totally based on the STM’s HAL + LL drivers that have uniformed APIs across all STM32 microcontrollers. In this way, you can use the code provided in the practical LABs in this series of tutorials and build it to your specific target microcontroller whatever it is, it should work!

ECUAL drivers we’ll be building include: [ Servo Motors – Keypad – LCD – HC-SR04 Ultrasonic – Joystick – and more.. ]. You can check them out if you’re curious or just keep following along with these tutorials.

That’s it for this short introduction to the STM32 HAL Library and CubeMX tool. In the next tutorial, we’ll get to know the hardware GPIO ports and pins. How it works and the internal circuitry and functionalities you can configure in various applications. Thereafter we’ll be able to start the first LAB in this series of tutorials and “Blink an LED!”.
