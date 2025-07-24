# Chintoiu Vladut-Andrei

## 30.06.2025
Revisited tour of Rust and started Rustlings

## 1.07.2025
Continued working on Rustlings

## 2.07.2025
Finished Rustlings and worked on the labs on a STM32F4

## 3.07.2025
Familiarized with Tock and tried to flash the STM32F4 with it. Continued with this on Monday

## 7.07.2025
Succesfully flashed the board with Tock and installed blink and c_hello on it using libtock-c. Could not make libtock-rs work.

I worked with Genan on identifying what should be written in order flash the LPC55S69 with a loop that keeps the nop open. I have focused on memory layout and ensured that nothing is missing.

We have worked on building and flashing the board with the looping script, however, sections are missing from the ELF file (like .text, .rodata, .data, .bss), which make flashing the build impossible. We shall further work on this issue tomorrow.

## 8.07.2025
We have solved the above issue with the help of our mentors, the issue being a missing line which included the linker script usage.

## 9.07.2025
Started reading up on the implementation of UART to the LPC55S69 board. I tried to obtain the needed file from the .svd to working, but without success. I have used svd2rust, which uses a different format from what we needed, so my colleague found a quick fix for svd2regs, which we needed.

## 10.07.2025
Started adapting the UART script by identifying the functions of the registers. Implemented part of the functions needed to make it work.

## 14.07.2025
Further read on the clocks needed to allow the USART peripherals to work. This raises the issue of needing an additional implementation for syscon and a general implementations of clocks. Additionally, flexcomm must also be implemented, to allow USART mode selection in the 8 communication interfaces.

## 15.07.2025
Started the implementation of USART, without creating the additional resources. Attempted to create a working prototype over the USART provided by the debugger. Setup was unsuccesful.

## 16.07.2025
Corrected the mistakes made in the previous day and succesfully implemented USART as a prototype. Next step is to implement encapsulate the methods used belonging to each peripheral (syscon and flexcomm).

## 17.07.2025
Started working on clocks.rs, providing higher level methods for enabling USART. Implemented functions for all the FLEXCOMM interfaces, beyond the one needed for my prototype (FLEXCOMM0).

## 21.07.2025
Cleaned up the code and generalized some of the traits for easier use.