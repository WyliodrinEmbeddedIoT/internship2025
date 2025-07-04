# Andrei Dragota

## 23 June 2025
During the day I recapped most of Rust's programming language intrinsics by going through https://tourofrust.com/TOC_en.html, finished 8 chapters out of 9.'
Wrote some notes and asked questions around the office for things I didn't catch on at first. Will finish last chapter tomorrow

## 24 June 2025
Finished the last chapter on Tour of Rust, started working on a issue on GitHub project regarding x86 architecture on Tock. Wrote a basic kernel with a VGA (text) buffer and added support for simple unit tests. Installed QEMU emulator to boot the kernel on a virtual machine to test it out, and to also write via serial UART on console. Tomorrow I will move on to the next topics regarding exceptions, timeouts, etc.

## 25 June 2025
Explored everything about CPU interrupts and exceptions. Wrapped up the testing part. Updated my kernel to support handling for double/triple faults, support for GDT, TSS, IDT, from the x86_64 crate. Ready to move on to hardware interrupts based on Intel 8259 PIC.

## 26 June 2025
Finished hardware interrupts, manage to solve deadlock + race conditions issues on my testing kernel. By also implementing the hlt instruction, I managed to get keyboard support on my kernel, now I can write "Hello World" and the system won't crash. Next, I read all about paging (theory + some implementation). Toyed around with address computation, seems difficult. I'll see tomorrow!

## 27 June 2025
Started working on implementing translation between physical and virtual addresses. Fixed an issue in my kernel where I couldn't invoke a private function from memory.rs to read the 4th page table's contents in main.rs. Moved on with implemeting address maping and frame allocation, will finish it next week. Also learnt how to use helix editor and [`zellij`](https://zellij.dev) window manager.

## 30 June 2025
Wrapped up paging implementation by creating a maper and a frame allocator. Moved on with heap allocation, learnt about static and local variables, implemented an allocator interface and a heap memory stack. Finally added and debugged testing framework from last week in order to add heap memory tests, took quite a while but it's working.

## 1 July 2025
Finally finished the whole memory management chapter. I learnt how to design memory allocators by implementing bump, linked lists and fixed-size block allocator. Moved on to the final chapter, multi-tasking. Fiddled with async/await feature and multitasking, will add soon support for this in my basic kernel, then I will learn a bit about pinning in this context. Learnt the file structure/architecture for TockOS. I should start implementing x86 support for VGA on Tock real soon!!

## 2 July 2025
After a week and a half I finished implementing a basic kernel, today I added the last bits of pinning concept, coming with cooperative multitasking, wakers and constructors. Cloned the Tock repo and fiddled with its directories and code architecture. I managed to solve a small bug that prevented me from booting tock kernel on qemu. 

## 3 July 2025
Started working on my task of implementing a VGA driver. Wrote the peripherals to enter VGA mode and declared the const in configs. I wrote some code in order to test the resolution implementation, still have some bugs as it renders the correct resolution, but nothing is shown on screen, could be a crate loading issue or maybe the buffer is overwritten. However, everything works fine in text mode, I can print colored letters and it's working fine (still no keyboard support for VGA though).

## 4 July 2025
Debugged and tested my implementation from previous day. I also started adding scrolling support, will flesh it out next week. Also opened my first pull request !!!  (it's in rough shape but I can fix most of the reported issues :D ) 
