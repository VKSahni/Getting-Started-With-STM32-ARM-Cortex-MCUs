# Getting-Started-With-STM32-ARM-Cortex-MCUs
Getting Started With STM32 ARM Cortex MCUs
In this introductory tutorial, we’ll get a closer look at the STM32 ARM-Cortex based microcontrollers. And it’s internal architecture, bused, and features. We’ll discuss the reset and clock control circuitry with the clock tree, which we’ll configure later on using CubeMX.
# STM32 ARM®-Based Microcontroller
The STM32 series of microcontrollers is one of the most popular ones among the 32-Bit microcontrollers. STMicroelectronics provides multiple of product lines for the STM32 parts. There is a low-power, mainstream, and high-performance product lines. And a more application-specific wide variety of parts that enables you to pick the right part for your project.
There are low-cost FullSpeed USB solutions, CAN, LIN, Ethernet, DCMI (Digital Camera Interface), and CryptoEngine for cryptographic applications, and much more powerful peripherals. Both digital and analog such as ADCs, DAC, OPamp, Comparators, etc.
The development boards we’ve selected for this series of tutorials are Nucleo32-L432KC and Blue Pill. Here is the hardware peripherals and ARM-Core highlight diagram for the STM32L432KC microcontroller part.
You can use the STMicroelectronics software tool called “STM32 MCU Finder”. This is basically a parametric searching tool that helps you easily find the convenient microcontroller with the required specs that you select in the GUI tool.
# ARM Cortex-M4 Processor + FPU(Arm® Cortex®-M4)
The Arm® Cortex®-M4 with FPU processor is the latest generation of Arm® processors for embedded systems. It was developed to provide a low-cost platform that meets the needs of MCU implementation, with a reduced pin count and low-power consumption, while delivering outstanding computational performance and an advanced response to interrupts.
The Arm® Cortex®-M4 with FPU 32-bit RISC processor features exceptional code efficiency, delivering the high-performance expected from an Arm® core. The processor supports a set of DSP instructions that allow efficient signal processing and complex algorithm execution.
Its single precision FPU speeds up the software development process and accelerates the target performance. With its embedded Arm® core, the STM32L432KC microcontroller can be used in a wide range of applications. As we’ll see throughout the course.
The other STM32F103C8 microcontroller has a Cortex-M3 core that lacks the FPU and DSP operations which can be a huge miss in certain applications, however, it’s much cheaper target MCU at the end of the day.
# Adaptive Real-Time (ART) Accelerator™
The ART Accelerator™ is a memory accelerator that is optimized for STM32 industry-standard Arm® Cortex® M4 processors. It balances the inherent performance advantage of the Arm® Cortex®-M4 over Flash memory technologies, which normally requires the processor to wait for the Flash memory at higher frequencies.
To release the processor near 100 DMIPS performance @ 80MHz, the accelerator implements an instruction prefetch queue and branch cache, which increases program execution speed from the 64-bit Flash memory. Based on the CoreMark benchmark, the performance achieved thanks to the ART accelerator is equivalent to 0 wait state program execution from Flash memory at a CPU frequency up to 80 MHz.
# Memory protection unit (MPU)
The memory protection unit (MPU) is used to manage the CPU accesses to memory to prevent one task to accidentally corrupt the memory or resources used by any other active task. This memory area is organized into up to 8 protected areas that can in turn be divided up into 8 subareas.
The MPU is especially helpful for applications where some critical or certified code has to be protected against the misbehavior of other tasks. It is usually managed by an RTOS (realtime operating system). If a program accesses a memory location that is prohibited by the MPU, the RTOS can detect it and take action.
# Firewall
The device embeds a Firewall that protects code sensitive and secure data from any access performed by a code executed outside of the protected areas. Each illegal access generates a reset which kills immediately the detected intrusion.
# Boot modes
At startup, BOOT0 pin or nSWBOOT0 option bit, and BOOT1 option bit are used to select one of three boot options:

Boot from user Flash

Boot from system memory

Boot from embedded SRAM

BOOT0 value may come from the PH3-BOOT0 pin or from an option bit depending on the value of a user option bit to free the GPIO pad if needed. A Flash empty check mechanism is implemented to force the boot from system flash if the first flash memory location is not programmed and if the boot selection is configured to boot from the main flash.
The boot-loader is located in system memory. It is used to reprogram the Flash memory by using USART, I2C, SPI or USB FS in Device mode through DFU (device firmware upgrade).
# System Architecture & Bus Matrix
The system mainly consists of 32-Bit Multilayer AHB Bus Matrix (Highlighted in Yellow) that interconnects the following hardware components:
# Five masters:
Cortex®-M4 with FPU core I-bus

Cortex®-M4 with FPU core D-bus

Cortex®-M4 with FPU core S-bus

DMA1

DMA2
