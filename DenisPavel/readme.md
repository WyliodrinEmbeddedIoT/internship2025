# Denis-Iulian Pavel
Github: LithTheFox

## 01 July 2025
Started the internship and began Tour of Rust and Rustlings.
Finished about half of Rustlings.

## 02 July 2025
Finished 3 quarters of Rustlings

## 03 July 2025
Finished Rustlings, installed and started using debian 12 bookworm as my main operating system
(I chose debian since ubuntu and debian were recommended for this intership as they seem to have no issues with the boards)

## 04 July 2025
Finished setting up debian with all necessary packages and features
Started working on [Merge ADC API #2](https://github.com/WyliodrinEmbeddedIoT/libtock-rs/issues/2) for libtock-rs
Encountered issues with the merge code.

## 07 July 2025
Finished the "Merge ADC API #2" with the PR [Merged ADC-API with the fix #3](https://github.com/WyliodrinEmbeddedIoT/libtock-rs/pull/3)
The issue encountered was with a listener test that was correctly assesing the value of the fake adc. I tried initially
to modify the argument order for the upcall function so that the listener would asses the value of the first
argument and it worked however this change conflicted with the tests in the actual peripheral adc api as they needed the sample
argument to be the third not the first. After consulting with one of the internship assitants I ended up modifying the listener test
such that it asses the third value for the sample and it worked perfectly with whatever value I'd set afterwards.
I also modified a clippy lint that cast an unnecessary usize variable as usize which was redundant.

## 08 July 2025
Started working on [Implement SPI asynchronous for LPC55 #2](https://github.com/WyliodrinEmbeddedIoT/embassy/issues/2) for embassy



