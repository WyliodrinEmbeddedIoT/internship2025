# Irina Chiorean

## 23 June 2025

Completed the Tour of Rust tutorial and familiarized myself with Rust concepts such as smart pointers, ownership, and related memory management features.

## 24 June 2025

Started and finished laboratory 0. 

Initially faced difficulties blinking an LED on the STM32F4, but subsequently advanced through Lab 2 and completed an exercise from Lab 4.

## 25 June 2025

Completed Lab 3 and worked with PWM and ADC on the STM32.
Started working on Lab 5 and finished 2 exercices.


## 26 June 2025

Completed all the labs (except 7 because it can't be done with the STM32F4).
Started working on rustlings and completed around 30% of it.

## 27 June 2025

Got to the 50% mark on the rustlings exercices.

## 30 June 2025

Got to the 80% mark on the rustlings exercices. 

## 1 July 2025

Finished the rustlings exercises at home. 

Set up a pc in the lab with ubuntu.
Chose my first task: "Add the lpc55 feature to the embassy-nxp crate" and started working on it. Familiarized myself with the idea of "flavors", "features", "custom metadata", "pac" and "metapac". 
Added a specific "lpc55" feature  and a compilation error in case there is no feature specified.

I ran into an issue because of Ubuntu where my user didn’t have permission to access the NXP board. It was fixed using a custom udev rule.
This is what I did to fix it:

1. By running "lsusb" I found the relevant line "Bus 001 Device 019: ID 1fc9:0090 NXP Semiconductors LPC-LINK2 CMSIS-DAP V5.224" .
  
2. I created a new udev rules file inside /etc/udev/rules.d/. I named it 55-nxp.rules (the 55 just determines the order in which udev loads the rules).
sudo nano /etc/udev/rules.d/55-nxp.rules

3. Inside 55-nxp.rules I added this line:

SUBSYSTEMS=="usb", ATTRS{idVendor}=="1fc9", ATTRS{idProduct}=="0090", MODE="0660", TAG+="uaccess"

## 2 July 2025

Finished my first issue and submitted it for review, then looked over the implementation of time drivers in embassy. 
Helped some of the others with the issues I have previously ran into.
