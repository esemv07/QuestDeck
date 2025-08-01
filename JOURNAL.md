---
title: "QuestDeck"
author: "esemv"
description: "A writerDeck style Cyberdeck design specifically for TTRPGs"
created_at: "2025-06-12"
---

Total hours so far: 53

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

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/89b0f252f0d627bbedb36bd3627d85c5cafb7154_pcb-15_06_2025.png" width="1000" title="Keyboard PCB No Routing">

`PCB: +4 hours`

***+ 4 hours***

### Time Spent on This Day: 8 hours 
`Schematic: 4 hours` `PCB: 4 hours`

<br><br>
## Day 3: 16th June 2025
`PCB`

I first did the routing for the keyboard as well as splitting it apart and adding board outlines.

I made sure that on each split both FPC sockets were at the same height to make sure the cables will be able to connect:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/7e8ce688e658a073f081f463d7137ddc5c5d7293_pcb-16_06_2025-1.png" width="1000" title="Keyboard PCB Separated with Routing">

`PCB: +3 hours`

I then routed the 'Dice Roller Screen' PCB which also has an FPC cable. This FPC cable was harder to route as it is much bigger. I had to also make sure that it was lined up with the Centre Keyboard FPC above it. Here's what the 'Dice Roller Screen' PCB looks like as well as the corresponding FPC on the Centre Keyboard:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/fbfcd1a2758ff04adc24220ccd931a4bf9449654_pcb-16_06_2025-2.png" width="400" title="Dice Roller Screen PCB"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/39b7510bf573c067688de72827506f44c6eb24c8_pcb-16_06_2025-3.png" width="410" title="Centre Keyboard FPC">

`PCB: +1 hour`

***+4 hours***

### Time Spent on This Day: 4 hours 
`PCB: 4 hours`

<br><br>
## Day 4: 21th June 2025
`Schematic` `PCB`

I added the 'Top Screen' PCB to the schematic. The mainboard is the Raspberry Pi Zero 2 W and it is powered by a 2400mAh LiPo Battery. I am using a TP4056 for a charging module with USB-C, and also with a MT3608 boost module for the charging system. It is also connected to the rest of the PCBs through another FPC connector. Here is what that looks like in my schematic:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/b3e2e2ee73751aca971d882cc937b9e537c1c095_schematic-21_06_2025-1.png" width="500" title="Top Screen Schematic">

For the USB connection of the keyboard, I used the USB breakout on the KB2040 but on the RPi the USB breakout is on the underneath of the board. I don't think it is feasible to use the underneath of the board as it will be soldered to the PCB.

I have a makeshift solution that I just have to hope will work. I am going to use a USB breakout like this:

<img src="https://m.media-amazon.com/images/I/51JgDElwvvL._AC_SL1000_.jpg" width="300" title="USB Module">

Plug it into the Pi and then run wires between the breakout and some pads I have put on the PCB. No idea if this will work but I suppose I will find out...

`Schematic: +2 hours`

I have wired it all up on the PCB and here's what it looks like:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/20658f6b72c7292f33134f8388e809b978d3e7b7_pcb-21_06_2025.png" width="500" title="Top Screen PCB">

`PCB: +1 hour`

***+3 hours***

### Time Spent on This Day: 3 hours 
`Schematic: 2 hours` `PCB: 1 hour`

<br><br>
## Day 5: 22th June 2025
`Research`

I did a whole lot of research on custom MBK keycaps and here's what I've figured out:

For my keycaps, I have some interesting sizes, such as 4.75u. Although 2.25u, 1.75u, and 1.25u are not considered odd sizes, the place I was going to get the custom keycaps from, does not have them. They only have 1u, 1.5u and 2u.

I can no longer use FK Custom for my custom keycaps, and as they are the only place I can find that do custom MBK keycaps, I am going to have to find another solution. I've looked for similar style Choc v1 low profile custom options but can't seem to find any.

My first thought is to change to Choc V2 which have a Cherry MX stem, as then there are many more options for custom keycaps. I don't particularly want to do this as they are slightly bigger, and it also just wasn't really my original goal.

I have looked for other low profile switch options so that I can get keycaps. I looked at Kailh X switches which are basically more DIYable Scissor Switches. 

<img src="https://ae-pic-a1.aliexpress-media.com/kf/HTB1p3CvLQzoK1RjSZFlq6yi4VXa9.jpg_220x220q75.jpg_.avif" width="250" title="Kailh X Scissor Switches">

Although they have very mixed reviews about the longevity of the switch, and will also be hard to add as a footprint to my PCB. Although they seem super interesting so maybe I will try them out for another project. I also did research into maybe making a membrane keyboard as that gives the option for being super low profile. I pretty quickly realised this isn't really possible and it would be very hard to make, get produced, and very expensive.

So I guess it's back to the Choc V1s. I did some research into how to make my own custom keycaps with legends, but this involves materials and skills I don't have. But what if I just 3D print them?

I think this is what I'll do. I can use multicolour inlay on the top of the keycap (printing top down) to give the legends. This also means for the keys I have such as Roll, I can fully design what the legend will look like in Fusion.

I have found [these keycaps](https://www.printables.com/model/549143-mobop-retro-inspired-keycap-set) which fit the vibe really well and are also flat on top making it much easier for the legends.

<img src="https://media.printables.com/media/prints/549143/images/4480174_4b2cdb35-0297-4858-813e-8e68bc6c560a/thumbs/inside/1600x1200/jpg/img_5996.webp" width="500" title="Retro Typewriter Choc Keycaps">

When I get to making the keycaps I can make the inlay legends in Fusion, which should not be too hard. But I'm not going to add them until later.

`Research: +5 hours`

***+5 hours***

### Time Spent on This Day: 5 hours 
`Research: 5 hours`

<br><br>
## Day 6: 28th June 2025
`CAD`

I first exported the PCBs as .STEP files from EasyEDA and imported them into Fusion to start the case.

I started modelling the case based on the original designs I had and here's what that looks like:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/8af223b39d4b246aac92f3808d6617e6ddba28b0_cad-28_06_2025-1.png" width="500" title="CAD-28/06/2025-1">

`CAD: +1 hour`

I realised there are a few issues with this design:

- First, I wanted the dice roller screen to slide out from under the keyboard, but with the height of the PCBs and the limited space, this will not be an option

- Second, if I tried fold the keyboard using this design, it would just get stuck as there is not enough space allowed for the hinge motion.

I will leave issue 1 for later, but attempt to address issue 2 now. I widened the hinge that is there as well as making a slider path that will have a pin meaning that the keyboard can slide further out as it folds preventing it from getting stuck.

Here's what that looks like so far:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/d0c639320425dee908219df5d107c0e47d818d34_cad-28_06_2025-2.png" height="250" title="CAD-28/06/2025-2"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/864e8e8c6a0f394e4346cbe4d8b0b2e3c78304c7_cad-28_06_2025-3.png" height="250" title="CAD-28/06/2025-3">

I'm pretty sure that should allow the keyboard to fold nicely... hopefully

`CAD: +3 hours`

***+4 hours***

### Time Spent on This Day: 4 hours 
`CAD: 4 hours`

<br><br>
## Day 7: 29th June 2025
`CAD`

I next modelled the enclosure for the top screen to go in, that will hinge to the main body:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/239cfb22102aae8c5d5d6ed78e78b40c16798a27_cad-29_06_2025-1.png" height="300" title="CAD-29/06/2025-1"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/c3af7e99c93be41d8af75a30b6e7cef942a63a90_cad-29_06_2025-2.png" height="300" title="CAD-29/06/2025-2">

I have decided for the dice roller screen, instead of having in slide out, it will also hinge and sit against the body when closed (as shown in the image above).

`CAD: +2 hours`

***+2 hours***

### Time Spent on This Day: 2 hours 
`CAD: 2 hours`

<br><br>
## Day 8: 30th June 2025
`CAD`

I first recloured everything in the CAD to make it more accurate to what I want it to look like:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/4a6c12a2cbb8e3e2273099f95df89f7fdd32aa81_cad-30_06_2025-1.png" width="500" title="CAD-30/06/2025-1">

I then realised the the top screen can hinge from the spot it it hinging from; it is currently connected to the bottom of the left and right keyboards, but when the keyboard opens, it can't connect to there.

In order to fix that, I can add a spine and connect it to that. The spine can then connect to the bottom of the centre keyboard which will stay in the same position the whole time.

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/7e2f4e0304e33701cfbf3e5a8fee5333aa87fcd0_cad-30_06_2025-3.png" height="300" title="CAD-30/06/2025-2"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/98128ed898b14f5c32ddf7fb62e75b95c8e88ecc_cad-30_06_2025-2.png" height="300" title="CAD-30/06/2025-3">

I also changed the design on the book cover and I think it looks pretty cool.

`CAD: +3 hours`

***+3 hours***

### Time Spent on This Day: 3 hours 
`CAD: 3 hours`

<br><br>
## Day 9: 1st July 2025
`CAD`

I blocked out a quick enclosure for the dice roller screen that will also hinge of the bottom of the centre keyboard:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/54bbe1b415dadab0b93fa1e530b34e929f0a91cd_cad-1_07_2025-3.png" width="500" title="CAD-1/07/2025-1">

`CAD: +3 hours`

I then added little hinges on the spine that will have a metal rod go through the middle to hold the parts together and allow the to hinge:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/f20f3ee76c252c49732338cefaf35d18cc3325c2_cad-1_07_2025-1.png" height="300" title="CAD-1/07/2025-2"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/abed224bf7038571b4d20ecd0711a48e4e1b15b1_cad-1_07_2025-2.png" height="300" title="CAD-1/07/2025-3">

`CAD: +2 hours`

***+5 hours***

### Time Spent on This Day: 5 hours 
`CAD: 5 hours`

<br><br>
## Day 10: 2nd July 2025
`CAD`

I remodelled the space for the top screen so that there is the right space for the screen and PCB:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/538cd4350233023ac947cc3dc42c819ac2ea1785_cad-2_07_2025-1.png" height="300" title="CAD-2/07/2025-1"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/4fb1e0a05cf718bf134387fc8ac1cf52fb97535e_cad-2_07_2025-2.png" height="300" title="CAD-2/07/2025-2">

`CAD: +2 hours`

I also remodelled the enclosure for the dice roller screen, so that it fits well between the keyboard hinges, and can be separated into 2 parts so that it can be put together:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/a67a1d6be60f965e4c0334c5bf85918b7c272185_cad-2_07_2025-3.png" height="300" title="CAD-2/07/2025-3"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/c125b47e3515edbaca8124fa86085bd3843a293c_cad-2_07_2025-4.png" height="300" title="CAD-2/07/2025-4">

I then separated it into 2 parts that screw together and and mounting spots for the PCB. I added screw holes on tabs off the side so that it can connect as securely as possible.

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/22608c1368aaff7f023d319573502f78cd6fe8a6_cad-2_07_2025-5.png" width="500" title="CAD-1/07/2025-5">

I also added a slot for the hinge to sit.

`CAD: +3 hours`

***+5 hours***

### Time Spent on This Day: 5 hours 
`CAD: 5 hours`

<br><br>
## Day 11: 8th July 2025
`CAD`

I designed the dice roller screen to look like a lock on the book. I am going to print it in gold filament because I think that will look super cool. Here's what that looks like, and also what it would look like without the lock part on it:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/d69014623e267fc5efa03c039b5d6f00e025f653_cad-8_07_2025-1.png" height="300" title="CAD-8/07/2025-1"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/f41d03d6489d0f3f79d070ddf6d574d2c60a25b3_cad-8_07_2025-2.png" height="300" title="CAD-8/07/2025-2">

Here's what the full CAD model looks like so far:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/58244dd715e07faa0dfe6c4dd9cabb6ea5899e11_cad-8_07_2025-3.png" width="500" title="CAD-8/07/2025-3">

I'm so happy with how it's looking so far!!!

`CAD: +2 hours`

***+2 hours***

### Time Spent on This Day: 2 hours 
`CAD: 2 hours`

<br><br>
## Day 12: 10th July 2025
`CAD`

As I already added the hinge slots to the dice roller screen, I also added them to the spine, as well as adding bigger hinges as I don't think the ones I had would be strong enough.

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/03e16a057abd437a1ecb395c244907a904c87c73_cad-10_07_2025-1.png" height="300" title="CAD-10/07/2025-1"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/02a2801615da2850a4ff925638523ce4e4fdc8b8_cad-10_07_2025-2.png" height="300" title="CAD-10/07/2025-2"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/4f3731a746be19b9bb3139df9558a6ef72433f05_cad-10_07_2025-3.png" height="300" title="CAD-10/07/2025-3">

I think I will just glue the hinges in rather than screwing them as there is no info on the product of the hole size or location. If that doesn't work then I will measure the hinge when it arrives and add the holes based on that.

For some reason I had a lot of issues with changing the size of the integrated hinge, it kept messing up the timeline and changing everything else which was really annoying. I ended up getting it working but it took way longer than it should have.

`CAD: +3 hours`

***+3 hours***

### Time Spent on This Day: 3 hours 
`CAD: 3 hours`

<br><br>
## Day 13: 19th July 2025
`Firmware`

I made a custom configuration for the keyboard using QMK. None of the configurator templates match my layout so I had to write the code myself.

I have written the firmware for the keys and added a spot for the macro for the 'roll' key. I want to configure the macro when I get the parts as I am having a really hard time figuring out the inputs without being able to test.

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/a21c801ee0ee17677331836a0366b544ae43eca0_firmware-19_07_2025-1.png" width="500" title="Firmware-19/07/2025-1">

I also added the layout of the keyboard in the firmware file as in the image above, because why not.

It's kinda exciting, I'm so close to finishing.

I'm next going to add the mounting for the keyboard PCBs and I think that is the last thing I need to do... hopefully

`Firmware: +3 hours`

***+3 hours***

### Time Spent on This Day: 3 hours 
`Firmware: 3 hours`

<br><br>
## Day 14: 30th July 2025
`PCB` `CAD`

I added mounting holes to the PCBs so that I can mount them to the case:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/57323536f914811dec7a305a5efddad53d6bc986_pcb-30_07_2025-1.png" width="500" title="PCB-30/07/2025-1">

I then added corresponding mounts for it on the case:

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/b09b07b028de605e3cc739c1b2b27fe9ffed4c04_cad-30_07_2025-1.png" height="300" title="CAD-30/07/2025-1"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/102e6aa40c3ac50bdc2e007bb2c5e97580266a26_cad-30_07_2025-2.png" height="300" title="CAD-30/07/2025-2">

I have done some final renders of what the QuestDeck looks like and I'm honestly so happy with this!!!

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/19c106db9431470c5a2ac108fad42a387e884791_cad-30_07_2025-3.png" height="300" title="CAD-30/07/2025-3"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/37f0036d1e122edd50f2dcf40fd76e1f781b7ee9_cad-30_07_2025-4.png" height="300" title="CAD-30/07/2025-4">

`PCB: +1 hour` `CAD: +2 hours`

***+3 hours***

## :partying_face::partying_face:

### Time Spent on This Day: 3 hours
`PCB: 1 hour` `CAD: 2 hours`
