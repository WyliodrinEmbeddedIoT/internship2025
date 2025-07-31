# Ioana Nedelcu

## 25 June 2025
Went through half of the Vue JS exercices, covered basic concepts such as reactivity and the use of `v-if`, `v-bind`, `v-on` and `v-for`.

## 26 June 2025
Finished the Vue JS exercices, delved into more complex topics like lifecycles and child components.

## 27 June 2025
Read through half of Tour of Rust. Found out some new ways to write certain pieces of code (ex. returning values, tuple-like structs) and learned about ownership and borrowing.

## 28 June 2025
Started on the rustlings exercices. Read a couple more chapters of Tour of Rust.

## 29 June 2025
Finished half of the rustlings exercices. These have been helpful in revising the material covered within Tour of Rust. 

## 30 June 2025
Cleaned around the office a little :) And more rustlings.

## 1 July 2025
Finished reading the last chapter of tour of rust. Did rustling exercices on options and error handling, which i found a litlte bit trickier. 

## 2 July 2025
Did rustlings exercices up to unit '18_iterators'. 

## 3 July 2025
Finished rustlings exercices at last. Started on the STM32f4 labs by setting up the board. Ran into an issue where despite our board appearing in the USB listing, the probe couldn't be found. We asked around and this problem turned out to be a pretty common one. In the end we got some help in changing the udev rules and 'Config.toml' file, which did the trick.

## 4 July 2025
Looked over the labs proper. We struggled for a while on exercice 9 of 'Lab 2 - GPIO', which involved making a function that takes a letter as an argument and displays it in morse code using 3 LEDs. After much testing we realised the problem stemmed from the fact that we hadn't included a pause between displaying each dot and dash, which explained why no matter which letter we called the function for, all LEDs only lit up once, at the same time. 

## 7 July 2025
Took up my [first issue](https://github.com/WyliodrinEmbeddedIoT/tockloader-rs/issues/45), which involves creating a github workflow CI action that automatically creates  an issue when a folder in the upstream repository is updated. For starters I followed the [Quickstart](https://docs.github.com/en/actions/get-started/quickstart) tutorial on workflows by GitHub to understand the basics of workflow creation. Looking through the examples and use cases in the documentation, I found one on [Scheduling issue creation](https://docs.github.com/en/actions/how-tos/use-cases-and-examples/project-management/scheduling-issue-creation), which might come in handy. Based on this I made a working prototype of the issue creation (based on time alone for now). Tomorrow I will have to modify this workflow to trigger based on repo updates.

## 8 July 2025
The issues are now created based on a trigger. At first I made it so the trigger is on any commit in the repo. After that I managed to make it file path dependent, though I had to change a lot of the code. What's left to do now is to implement this on the actual 'tockloader-rs' repository. That being said I still have the problem of my cron job not running at all. Tried a few time intervals but still nothing. I've looked into it and it might just be a huge delay on GitHub's part. I'll have to see if anything changes by tomorrow.

## 9 July 2025
Indeed, the cron scheduling was just a delay on GitHub's part. I checked the log and all of the scheduled workflows ran. Integrated the separate 'bash' script part of the workflow directly into the 'yml' for less file clutter. Had my solution checked and there are quite a few modifications that need to be made. I drafted a flowchart on paper in order to help me figure out the new workflow algorithm (as well as aid in explaining my thought process more easily). It was recommended to me to use the commit hashes in order to figure out which commits were already accounted for, as this was an aspect my intial solution overlooked.

## 10 July 2025
Wrote a list of the steps that I need to take in my implementation. Managed to extract the 'sha' of a commit, as well as the one stored in a file. Managed to list all shas up until the one stored in the file.

## 11 July 2025
In the end I've limited my solution to only one workflow, as there were fields I needed in the issue creation that I couldn't pass from one workflow to another. Stored the commit messages as well. Shortened the shas that will be in the issue body. Succesfully created issue listing all of the commits that need updates. Made the check for if issue already exists or not. Editting an issue if it already exists now works. A comment now appears notifying the user if the list was changed.

