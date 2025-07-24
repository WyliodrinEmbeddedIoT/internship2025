# Genan Omer

## 30 June 2025

Finishing Tour of Rust and Rustlings exercises.

## 1 July 2025

Doing most of the labs using a STM32. Recalling what I learned.

## 2 July 2025

Reading more about TockOS and technical details about the NXP-LPC55 board. Starting to work on a issue related to a NXP board really soon.

## 3 July 2025

Installing Tock, libtock-c, and libtock-rs, and starting to experiment with them (building a small app, flashing an STM32F429ZI with Tock), as well as reading more about the TockOS architecture.

## 4 July 2025

Reading about how to write the TockOS kernel and how to boot the NXP LPC55 board. Next week, I will start working on the issue alongside Vlad.

## 7 July 2025

Started working on the [issue](https://github.com/WyliodrinEmbeddedIoT/tock/issues/18) today. I began by learning how to open the debug probe on the board. Then I started looking into the memory mapping of the board and began writing the layout.ld file.

After creating the layout.ld file, Vlad identified the architecture for the Cortex-M33 and added it to Tock. Before that, we began writing the other required components (the chip file and the board file), but we ran into a problem.

After building the program and attempting to flash it to the board using probe-rs, we encountered an error related to the build file. Specifically, the sections are not being created properly on the chip, and the flashing process is failing.

We tried several solutions, but haven’t made any progress yet. We’ll look into it further tomorrow.

## 8 July 2025

Today we successfully booted the NXP-LPC55 board for the first time.

The issue preventing it from booting was due to a missing `build.rs` entry in the board's `Cargo.toml` manifest file. Once we added the missing entry, the board booted without any problems.

After confirming the boot process, we tested the board using semihosting to verify functionality. Everything worked as expected.

## 9 July 2025

Today I picked up a new task focused on working with GPIO for the NXP-LPC55 board.

I began by reviewing how GPIO is implemented on other boards and examining how the relevant registers are defined. To proceed, I searched for the `.svd` file for the LPC55 and successfully found it online.

However, I ran into an issue with the `svd2regs.py` script—it wasn’t working as expected. After several attempts to debug the problem, I decided to pause and revisit it with a fresh perspective tomorrow.

## 10 July 2025

Today I focused on resolving the issue with the `svd2regs.py` script. The solution was to roll back the `cmsis-svd` package to version `0.4`, which restored compatibility and allowed the script to run correctly.

With the script working, I successfully generated the GPIO register definitions from the board's `.svd` file. After that, I started implementing basic GPIO operations and began defining the board’s pins accordingly.

## 11 July 2025

Today, I spent time reading and deepening my understanding of how GPIO and IOCON work on the NXP-LPC55 board. I focused on grasping the configuration flow and how these components interact.

This helped me clarify the next steps needed for implementing GPIO functionality on the board.

## 14 July 2025

Today, I opened a pull request on the main Tock repository to address the issues with the svd2regs.py script.
My solution was to set up a uv package manager project, which ensures all dependencies are installed with the correct versions. This approach improves reproducibility and avoids version-related breakages in the future.
The pull request can be seen [here](https://github.com/tock/tock/pull/4507).

## 15 July 2025

Today, I began implementing the IOCON register definitions along with methods to configure pin modes.

After completing the IOCON setup, I attempted to blink an LED on the board as a basic test. However, nothing happened, so I started investigating the issue. By the end of the day, I suspected the problem might be related to the `.elf` file’s entry point.

I plan to dive deeper into this and work on a fix tomorrow.

## 16 July 2025

Today, I resumed work on blinking the LED and investigated the suspected issue with the `.elf` file’s entry point. It turned out the real problem was that I had forgotten to initialize the stack memory, which prevented the program from flashing to the board. After fixing this, the LED blinked successfully—confirming that the basic setup is now functional.

Next, I moved on to implementing GPIO interrupts and attempted to test them using a button. I defined the necessary interrupt logic, but the button input did not trigger as expected. I plan to investigate the issue further tomorrow.
