# QuestDeck
A writerDeck style Cyberdeck design specifically for TTRPGs


## What is it?
This project is a version of a writerDeck I have designed specifically to be used for TTRPGs. It has a custom keyboard as well as all custom PCBs and runs on Raspberry Pi Zero 2 W. The keyboard is foldable and the whole thing folds down into a book style case. It a Dice Roller OLED screen that connects to the keyboard, meaning that when the 'Roll' key is pressed, it will roll dice on the screen for you.

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/19c106db9431470c5a2ac108fad42a387e884791_cad-30_07_2025-3.png" width="500" title="Full CAD Render">

## Why did I make this?

I love playing TTRPGs such as DnD as well as solo TTRPGs. I like to take notes on the game and it is nice to type them out, but the issue I often experience is getting distracted by other tabs, notifications, etc. This device is a no distractions writing device meaning that I can take the noted I want without the normal distractions. I also think it is super cool to be able to have a writing tool designed to fit the theme of TTRPGs so I made the case as nice as possible to achieve this goal.

## Pictures

### Schematic

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/84754e958fff1d9ef64773328dd6946d347f13b3_screenshot_2025-08-01_at_12.20.29___pm.png" width="500" title="Schematic">

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/f440bc7be09aa80cc5cec1b9e188d7822c974704_centre_keyboard_schematic.png" width="800" title="Centre Keyboard Schematic">

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/5e15db86e6071026def67b1085b77fc96b00f43b_left_keyboard_schematic.png" height="400" title="Left Keyboard Schematic"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/ad3fea6cada88b7da7d11f8fde77448d5b9e20b6_right_keyboard_schematic.png" height="400" title="Right Keyboard Schematic">

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/6f4e63aa30371dda9464ff7aa41862dbd2293c1e_top_screen_schematic.png" height="400" title="Top Screen Schematic"> <img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/773720e35ea70148d96d6dbacf18e6107f6d0e15_dice_roller_screen_schematic.png" height="400" title="Dice Roller Screen Schematic">

### PCB

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/6dd18a86aa430aa352974118f8e90609b239d0bb_screenshot_2025-08-01_at_12.18.39___pm.png" width="500" title="PCB">

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/ec0094416123911add4360ee3c47d36425301ba4_pcb_3d_front.png" width="500" title="PCB">

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/3efee8171b7aaebf96510910b58edb4fe920df14_pcb_3d_back.png" width="500" title="PCB">

### Final CAD

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/19c106db9431470c5a2ac108fad42a387e884791_cad-30_07_2025-3.png" width="500" title="Final CAD 1">

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/37f0036d1e122edd50f2dcf40fd76e1f781b7ee9_cad-30_07_2025-4.png" width="500" title="Final CAD 2">

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/58244dd715e07faa0dfe6c4dd9cabb6ea5899e11_cad-8_07_2025-3.png" width="500" title="Final CAD 3">

### Firmware

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/a21c801ee0ee17677331836a0366b544ae43eca0_firmware-19_07_2025-1.png" width="500" title="Firmware">

## Bill of Materials

### Total Cost: $175.51USD ($270.17AUD)

|         Category         |               Item                | Price (AUD) | Shipping |  Quantity  |      Vendor      | Notes/Considerations |         Link         |
|--------------------------|-----------------------------------|-------------|----------|------------|------------------|----------------------|----------------------|
|      Keyboard PCBs ↓     |   Kailh Choc Low Profile Switch   |    $44.19   |   Free   | 1 x 70pcs  |    AliExpress    |                      | [Kailh Choc Low Profile Switch](https://www.aliexpress.com/item/1005008576630923.html) |
|                          |           1N4148 Diodes           |    $2.84    |   Free   | 1 x 100pcs |    AliExpress    |                      | [1N4148 Diodes](https://www.aliexpress.com/item/4000142272546.html) |
|     Top Screeen PCB ↓    |       Raspberry Pi Zero 2 W       |    $29.45   |   Free   |     1      | Core Electronics | Somehow cheaper than AliExpress and is local | [Raspberry Pi Zero 2 W](https://core-electronics.com.au/raspberry-pi-zero-2-w-wireless.html) |
|                          |     3.7V 2400mAh LiPo Battery     |    $21.95   |   Free   |     1      | Core Electronics | Cheaper AliExpress options don't deliver until September | [3.7V 2400mAh LiPo Battery](https://core-electronics.com.au/polymer-lithium-ion-battery-2400mah.html) |
|                          |      Micro USB Plug Breakout      |    $13.99   |   Free   |  1 x 4pcs  |     AmazonAU     | Only option but should arrive July 30 - Aug 5 so hopefully it comes in time. | [USB MicroB Plug Breakout Board](https://www.amazon.com.au/Treedix-Breakout-Connector-Compatible-Electronics/dp/B09W2QHL2P) |
|                          |   Type-C TP4056 Charging Module   |    $1.34    |   Free   |     1      |    AliExpress    |                      | [DIY Type-C USB 5V 1A 18650 TP4056](https://www.aliexpress.com/item/1005008058129330.html) |
|                          |        MT3608 Boost Module        |    $2.79    |   Free   |     1      |    AliExpress    |                      | [MT3608 Boost Module](https://www.aliexpress.com/item/1005006361814667.html) |
|                          |     24 Pin FPC Cable Connector    |    $1.17    |   Free   |  1 x 5pcs  | LCSC Electronics | This may be wrong, need to check | [BOOMELE(Boom Precision Elec) 0.5-24P FG](https://www.lcsc.com/product-detail/FFC-FPC-Flat-Flexible-Connector-Assemblies_BOOMELE-Boom-Precision-Elec-0-5-24P-FG_C20688.html) |
|                          |        Battery Cable Socket       |    $1.85    |   Free   |     1      | Core Electronics | This may be wrong, need to check | [JST Right-Angle Connector - SMD 2-Pin](https://core-electronics.com.au/jst-right-angle-connector-smd-2-pin-black.html) |
|                          |      4.2inch E-Paper Display      |    $39.19   |   $5.86  |     1      |    AliExpress    |                      | [4.2 inch 3-Colour E-Ink display module (400x300 Pixels)](https://www.aliexpress.com/item/1005008589532618.html) |
| Dice Roller Screen PCB ↓ |         Adafruit KB2040           |    $20.05   |   Free   |     1      | Core Electronics |                      | [RP2040 Kee Boar Driver](https://core-electronics.com.au/adafruit-kb2040-rp2040-kee-boar-driver.html) |
|                          | OLED Display 128X32 0.91" SSD1306 |    $3.42    |   Free   |     1      |    AliExpress    |                      | [0.91 inch OLED Display Module - White](https://www.aliexpress.com/item/1005006010896161.html) |
|                          |    MCP23017-E/SO I/O Expander     |    $4.79    |   Free   |     1      |    AliExpress    |                      | [MCP23017-E/SO SOP28](https://www.aliexpress.com/item/1005008727662692.html) |
|                          |  Metal Film Resistors 4.7kΩ 0.25W |    $0.48    |   Free   |  1 x 50pcs | LCSC Electronics |                      | [UNI-ROYAL(Uniroyal Elec) MFR0W4F4701A50](https://www.lcsc.com/product-detail/Through-Hole-Resistors_UNI-ROYAL-Uniroyal-Elec-MFR0W4F4701A50_C57204.html) |
|     PCB Connectors ↓     |    26 Pin FFC Cable Connector     |    $7.14    |   Free   |  1 x 2pcs  |    DigiKey Aus   |                      | [FH12-26S-0.5SH(55)](https://www.digikey.com.au/en/products/detail/hirose-electric-co-ltd/FH12-26S-0-5SH-55/1110323?srsltid=AfmBOopqF7o7ptaexeaPUv0DdIia_AySKFMMV1k5vwqKbBNBlBynJ4EH) |
|                          |     9 Pin FFC Cable Connector     |    $7.44    |   Free   |  1 x 4pcs  |    DigiKey Aus   |                      | [FH19C-9S-0.5SH(10)](https://www.digikey.com.au/en/products/detail/hirose-electric-co-ltd/FH19C-9S-0-5SH-10/4283425?srsltid=AfmBOoqcyKZkMxO_LfuhkB4uOfiW8o3IG8r2A8k8QkMFRSA8k5cvBsd-) |
|                          |    10 Pin FFC Cable Connector     |    $4.36    |   Free   |  1 x 2pcs  |    DigiKey Aus   |                      | [FH12-10S-0.5SH(55)](https://www.digikey.com.au/en/products/detail/hirose-electric-co-ltd/FH12-10S-0-5SH-55/1110314?srsltid=AfmBOoqEdsP7pIlvfwTyiOzf9GYr_4whu2x5bs80QqxoZjZm51vtzrAO) |
|          PCBs ↓          |         Centre Keyboard           |    $15.09   |  $12.66  |  1 x 5pcs  |      JLCPCB      |                      | N/A |
|                          |          Left Keyboard            |    $4.98    |   $2.33  |  1 x 5pcs  |      JLCPCB      |                      | N/A |
|                          |          Right Keyboard           |    $4.98    |   $2.33  |  1 x 5pcs  |      JLCPCB      |                      | N/A |
|                          |        Dice Roller Screen         |    $4.98    |   $2.33  |  1 x 5pcs  |      JLCPCB      |                      | N/A |
|                          |            Top Screen             |    %15.71   |  $12.10  |  1 x 5pcs  |      JLCPCB      |                      | N/A |

## About the Design Process

You can find my whole designing process in my [Journal.md](https://github.com/esemv07/QuestDeck/blob/main/JOURNAL.md) file, and my parts list with links in my [BOM.md](https://github.com/esemv07/QuestDeck/blob/main/BOM.md) file.

I designed this project for [Highway](https://highway.hackclub.com/), a [Hackclub](https://hackclub.com/) program where you can get grants for hardware projects you design.

<img src="https://hc-cdn.hel1.your-objectstorage.com/s/v3/0bbcca68ffa3845300bb76940f8ad91fd53d2d68_06-30-2025-1618.png" width="300" title="A badge of a Cerberus and a raccoon laughing together, with the text HIGHWAY and HACK CLUB beside them.">
