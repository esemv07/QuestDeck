---
title: "QuestDeck"
author: "esemv"
description: "A writerDeck style Cyberdeck design specifically for TTRPGs"
created_at: "2025-06-12"
---

Total hours so far: 14

## Day 1: 14th June 2025
`Research` `Planning`

I did some research on [r/writerDeck](https://www.reddit.com/r/writerDeck/) to see some existing designs, their use and the types of software they use. I was particularly inspired by [this design](https://www.reddit.com/r/writerDeck/comments/1jg2ka8/anyone_seen_one_of_these_before/), which makes me want to make something foldable and compact so that it is portable.

I'm not sure how possible it is to make a keyboard that is easily foldable like that. Maybe scissor switches would work but I don't think they are possible for DIY, or even a membrane keyboard but it doesn't seem very plausible either. I also really like this design:

<img src="https://i.ebayimg.com/images/g/iNoAAOSwDphfteDW/s-l1200.jpg" width="350" title="Pomera DM30 writerDeck">

Both the designs I really like are from Pomera. I think I will try using Low Profile keyswitches and see if I can make a case that accomodates folding. The overall design will be a lot thicker but I still think it could be really cool.

`Research: +3 hours`

I also want to have a slide out screen at the bottom which will be a 'dice roller', so one of the keys will activate it, and you can choose how many sides it has and roll it. I will make it run off a Raspberry Pi Zero 2 W or Zero W, and then I will have the custom keyboard connected to a Adafruit KB2040 (RP2040) using its USB Breakout.

I drew a rough design based on these features:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/1e48ab7b731c3a147a0b578a439a8ea456f77063_img_1529.png" width="500" title="Full Design Sketch">

I also drew a design of the keyboard folding mechanism made for a mechanical keyboard thickness:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/ad551fe025b5f021f1bb5f1c499b639e1ebbfe19_img_1530.png" width="500" title="Folding Design Sketch">

I think I will use Kailh Choc V1 switches and then I could use custom MBK keycaps from [FK Custom](https://fkcaps.com/keycaps/mbk).

`Research: +2 hours` `Planning: +1 hour`

***+6 hours***

### Time Spent on This Day: 6 hours 
`Research: 5 hours` `Planning: 1 hour`

<br><br>
## Day 2: 15th June 2025
`Schematic` `PCB`

I wanted to try and smash out the keyboard part of the schematic as I already have experience designing keyboard schematics so it shouldn't be too hard. First I decided where the keyboard would be split and what special keys (such as Roll for the dice roller) I would have for it. I used [Keyboard Layout Editor](https://www.keyboard-layout-editor.com/) to make the layout:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/31d78fc3b6d83df66f42fd761ebc0d09918d2196_keyboard-layout.png" width="1000" title="Initial Keyboard Layout">

I then designed the schematic around this design. I named all the keys to make everythin easier to keep track of:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/8488722ce3b4808e45d48003f7c28e3f2e806d56_schematic-15_06_2025-1.png" width="1000" title="Initial Keyboard Schematic">

I decided to use the KB2040, an RP2040 based board, for my keyboard. This is because it has USB breakout meaning that I can pass the USB signal from the KB2040 to the Raspberry Pi through the PCB, rather than having to plug it in and manage those wires. This just helps with the size constraints of the project.

I will put the KB2040 on the 'Dice Roller Screen' PCB as there is not enough space on the keyboard. I can pass the row/column signals through an FPC cable from the keyboard to the KB2040. On that PCB there will also be a 128x32 OLED display which will display the dice rolling. I have also used this before in my Hackpad so it shouldn't be to hard.

I will have to use an IO Expander to handle all these signals as the KB2040 does not have enough pins. Again, I have used this before. Here is what the FPC to the 'Dice Roller Screen' PCB part looks like:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/40a6ac7d228b56fc87976369a3e732df78b00519_schematic-15_06_2025-2.png" width="350" title="Dice Roller Screen PCB">

And the whole thing:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/c5c4de78c4a383bba08c6a83c77156618eb4082d_schematic-15_06_2025-3.png" width="1000" title="Schematic So Far">

Next I will handle how the keyboards will be on separate PCBs. I can again use FPC cables to pass the signals to the centre PCB. Here is what that looks like:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/9e11599ea36befb1c0a37b82192a368c5de49a5b_schematic-15_06_2025-4.png" width="400" title="Separated Keyboards Left"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/e31712bb97d1e7f257610da8c80243b7e5bc127e_schematic-15_06_2025-5.png" width="252.5" title="Separated Keyboards Centre">

`Schematic: +4 hours`

***+ 4 hours***

I decided to attempt the long process of putting all the keys in their correct spots with all the spacing for the PCB. 

Because I decided to use Choc v1s there weren't good footprints in EasyEDA for the different size keys. I decided to instead use 1u footprints for all of them and manually calculate the spacings.

For the initial PCB placings I decided to just make it as one unified keyboard and then I can separate them after and add the board outlines for each. Here's what it looks like as the one part keyboard without the routing (ratlines hidden):

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/89b0f252f0d627bbedb36bd3627d85c5cafb7154_pcb-15_06_2025.png" width="1000" title="Dice Roller Screen PCB">

`PCB: +4 hours`

***+ 4 hours***

### Time Spent on This Day: 8 hours 
`Schematic: 4 hours` `PCB: 4 hours`

<br><br>
