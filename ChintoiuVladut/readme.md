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