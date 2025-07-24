# Roi Bachynskyi

## 23 June 2025
- Made a walkthrough of Tour of Rust and refreshed what I learnt during the labs (for, if, match, Option, Result, etc.)
- Read more Ownership and Borrowing which I didn't understand during the labs
- Explored Smart Pointers
- Explored the difference between ```&str``` and ```String```

## 24 June 2025
- Completed the MA Lab 0 to solidify knowledge gained yesterday
- Flashed STM32
- Completed tasks from MA Labs 2 and 4 (only LEDs and a button)


## 25 June 2025
- Completed the MA Lab 3 to check PWM and ADC on STM32
- Completed the Morse code exercise from MA Lab 2 which I missed and spent 1 hour on it (no_std environment demands another approach to Strings)
- Started the MA Lab 5 and started struggling with SPI, continue tommorow

## 26 June 2025
- Completed MA Lab 5 and MA Lab 6, SPI and I2C were revisited
- Reached 45/94 exercise from Rustlings

## 27 June 2025
- Reached 69/94 exercise from Rustlings
- Started to learn how to use Helix Editor
- Started organizing the workspace

## 30 June 2025
- Completed Rustlings 
![Rustlings Fe-nish](https://github.com/user-attachments/assets/0c2fa26a-1e5a-485a-a8a6-1218551ee443)

- Moved to the lab computer and installed Ubuntu
- Installed i3 window manager to start learnign no-mouse way of using the computer and OS
- Chose my [first issue](https://github.com/orgs/WyliodrinEmbeddedIoT/projects/1?pane=issue&itemId=116432064&issue=WyliodrinEmbeddedIoT%7Cembassy%7C4)
- Flashed the NXP board

## 1 July 2025
- Tried to flash the examples for the NXP Board: `blinky_nop` worked as intended, `button_executor` didn't print anything
- Spent 1 hour trying to understand what is wrong in the second example
- Explored `pint.rs` and `gpio.rs` files
- Thanks to George, the problem was found: allegedly, the asyncronous program didn't work because of the secure and non-secure mode. The only thing that could fix it is 1) flashing 2) `probe-rs attach` 3) pressing the reset button
- Explored the `fmt` module in `embassy-rp` which was used in `embassy-nxp`
- Not finished writing the code for features because of feature propagation 

## 2 July 2025
- Read a half of the book about macros ([link](https://lukaswirth.dev/tlborm/introduction.html)) to understand what happens in `fmt.rs`
- Thanks to George, understood the logic behind `defmt` and `log`
- Implemented `log-to-defmt` feature
- Closed my first issue

## 3 July 2025
- Chose my new [issue](https://github.com/WyliodrinEmbeddedIoT/embassy/issues/3) 
- Read a chapter about USART to understand how it works on this board
- Made some changes in the pull request as George asked me
- Started reading `embassy-rp` implementation of UART

## 4 July 2025
- Found a [pinout](https://mcuxpresso.nxp.com/en/pins) for LPC55S69 board (the datasheet is indeed awful)
- Wrote down pins for UART for each Flexcomm
- Found an instruction how to work with USART on LPC55S69 (planning to work on the implementation during the weekend)
- Explored `lpc55-pac`  

## 5-17 July 2025
- On vacation with my family

## 18 July 2025
- Fixed last problems in my ```log-to-defmt``` issue, rebased the changes from ```embassy``` GitHub repository and started my first [PR](https://github.com/embassy-rs/embassy/pull/4416)
- Started to implement USART following the documentation advice (got a bit complicated)

## 21 July 2025
- Dirbaio asked to remake the commit
- The initial guess was the correct one, therefore I read `fmt.rs` in `embassy-rp` several times once again, I added one more macro (`unimplemented!()`) that wasn't introduced in `embassy-rp`
- Dirbaio approved my PR, yay!

## 22 July 2025
- Started to work on USART once again
- Implemented writing to TX and reading from RX in loopback mode
- Tried to figure out why it didn't work physically, but failed, continue tomorrow 

## 23 July 2025
- Tried to debug my USART code and see what is wrong
- Currently, it's failing to work in normal mode (instead of loopback mode), something is blocking the signal
- Tried to debug it using Arduino Uno as a slave, but it didn't work out. Then, I thought the problem was in USART connection with the computer, but sadly, not.
- Denis told me to look at `lpc-hal`, George suggesed looking at C-implementation
- Helped Irina with her `nxp-pac` and `chiptool` (unfortunately, it doesn't have any documentation)
