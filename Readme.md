### Cygnus ZMK config template for the Seed XIAO BLE microcontroller


This repo contains the zmk shields required to use a cygnus with a Seed XIAO BLE microcontroller.    
The original cygnus repo can be found [here](https://github.com/juhakaup/keyboards/tree/main/Cygnus%20v1.0)   
All credit goes to the original creator [juhakaup](https://github.com/juhakaup). This is just a zmk config template that adds support for the Seeed XIAO BLE.

## Motivation
- It's quite simple: The Seeed XIAO BLE is significantly cheaper than a nice! nano v2.

### Wiring
This is the pin out for the xiao ble
![wiring](https://files.seeedstudio.com/wiki/XIAO-BLE/pinout2.png)

This config uses pin 0-3 for the rows and pin 4-8 for the columns.      

### Instructions


#### Reset button
The reset pins are on the back of the controller. (More detailed instructions can be found in the original build guide)   
![reset](https://files.seeedstudio.com/wiki/XIAO-BLE/back-pinout-5.jpg)


### Battery
Like the reset pins the battery pins are also at the back of the controller.   
**Check polarity before connecting the battery.**   
Solder your battery's - wire to the BAT- pin and your battery's + to a switch, which is connected to the BAT+ pin. This way you can switch the keyboard on an off. There should be more detailed instructions in the origina build guide.


#### Rows
1. Solder the first row ( which is the top one ) to the first pin (D0).    
2. Repeat this for the other rows going top to bottom from D0 to D3.


#### Columns
1. Solder the first column ( which is the leftmost one, or the purple on in my image ) to the pin D4.
2. Repeat this for the other columns going left to right from D to D8.




### Images of wiring 
(sorry for the poor image quality)


This is the wiring on the back of the keyboard. For a more detailed guide please look at [juhakaup's](https://github.com/juhakaup/keyboards/tree/main/Cygnus%20v1.0) build guide.
![wiring](./imgs/wiring.png)


As you can see in the picture. The black wire is connected to the first pin. As depicted in the image above, the black wire is connected to the first row of the keyboard. Following the principle all the following rows are connected to the controller in that order.   

The same goes for the columns. As seen in the image above, the purple wire is connected to the leftmost column. Following the principle all the following columns are connected to the controller in that order.


Admittedly the wiring is a bit messy. But it works decently well.
Additionally as documented in the original build guide, you can use printed brackets to secure the controller in place. Due to a broken printer I have not been able to print them, but the assembly should be quite straight forward.
![controller_wiring](./imgs/controller.png)

You should be able to repeat this process for the right side of the keyboad. The wiring is the same. Row 1 should still be connected to D0 and so on.

This is the final assembled version
![assembled](./imgs/assembled_cygnus.png)  


### Dongle
If you want to use a dongle with this keyboard please take a look at this branch: [dongle branch](https://github.com/vuoz/cygnus-xiao-ble/tree/dongle)

### Modifying the firmware
1. Fork the repo
2. Clone the repo to your computer
3. Change the config files in ./config
4. Rebuild using github actions ( by pushing to the repo )
5. Flash the firmware to the keyboard

### Flashing the firmware

1. Connect the keyboard to your computer.
2. Press the reset button on your keyboard twice. This will put the keyboard into bootloader mode.
3. Drag you firmware file onto the keyboard. It should be recognized as a USB drive.
4. Done


### Connecting to the computer
1. Flip the power switch on the the back of the keyboard case.
2. Go to your computer's bluetooth setttings.
3. Now you should be able to see a keyboard with the name "Cygnus" available.
4. Follow the instructions to pair the keyboard with your computer.
## Credits
- keymap, overlay and dtsi files are inspired by splitkb's corne keyboard [here](https://github.com/zmkfirmware/zmk/tree/main/app/boards/shields/splitkb_aurora_corne). Thanks to their work, I was able to port this keyboard to the Seeed XIAO BLE quite easily.
- the keyboard was designed by [juhakaup](https://github.com/juhakaup). All credit goes to his amazing work. This repo just contains a zmk config template to use the keyboard with Seed XIAO BLE microcontrollers
- Thanks to the ZMK team for their amazing work on the firmware and for making it so easy to design custom shields.
