# Build Guide

![picot_o44_main00](/images/main_00.jpg)

This is a build guide for picot_o44.  

picot_o44 is a 40% ortholinear keyboard using picot5400, which is the original module with RP2040 microcontroller and PMW3600 trackball sensor. 25mm or 34mm trackball is compatible.
To begin with, please make sure you read this build guide carefully and you have everything you need before you start to assemble.


## Parts
### Parts Included

|Parts|No.|Notes|
|---|---|---|
|PCB|1||
|Switch Plate|1||
|picot5400|1||
|Unified Daughter Board|1||
|Sensor (PMW3360)|1||
|JST Cable|1||
|FFC|1||
|M2 Spacer 3.5mm|16||
|M2 Screw 3mm|24||
|M2 Screw 5mm|8||
|Rubber Feet|4||
|Bearing Roller|3||
|Stainless Pin|3||
|Silicone Tube (Thin)|1||
|Silicone Tube (Thick)|1||
|Magnet|8||
|3D Printed Case|1||
|3D Printed Ball Case (Base + Cover)|1||



### Additional Required Parts

|Parts|No.|Notes|
|---|---|---|
|Keyswitch|Max 44|MX|
|Keycap|Max 44|MX|
|2U Stabilizer|0~3||
|Rotary Encoder + Knob (D18mm or less)|0~2|Optional|
|Trackball 34mm or 25mm|1||
|USB-TypeC Cable|1||


## Assembly
### Parts Check

  First, please make sure that you have all the parts listed above. If the PCB comes with tabs, break off the tabs and lightly file the cut surfaces.


### picot5400

  Please visit [picot5400 build guide](https://github.com/aki27kbd/picot5400/blob/main/doc/buildguide.md), and solder/assemble parts related to picot5400.  

### PCB

  If the switch sockets are not soldered on the board, solder the sockets.  
  If rotary encoders are to be installed, solder them at this step.  
  ![picot_o44_bg_pcb_1](/images/bg_pcb_1.jpg)  

  If stabilizers are to be installed, put them on the PCB at this step.

  Insert the switches into the PCB while attaching them to the switch plate. Be careful not to bend the legs of the switches.  
  ![picot_o44_bg_pcb_2](/images/bg_pcb_2.jpg)  

  Cut 8 pieces of the thicker silicone tube about 4mm long. They can be easily cut with scissors, but be careful to keep the cut surfaces as flat as possible.  
  ![picot_o44_bg_pcb_3](/images/bg_pcb_3.jpg)  

  Pass the spacers through the cut-out silicone tubes.  
  ![picot_o44_bg_pcb_4](/images/bg_pcb_4.jpg)  

  Insert the spacers with silicone tubes in 8 places between the switch plate and the PCB, and screw them in place from the top and the bottom with 3mm screws.  
  ![picot_o44_bg_pcb_5](/images/bg_pcb_5.jpg)  

  By placing spacers in all eight locations, rigid and hard key feel is achieved. Removing the spacers from the center four locations and placing spacers only in the four corners will result in a softer key feel. Adjust to your preference.

### Assembly

  First, install the daughter board in the case.

  Fix the spacers in four places with 3mm screws from the bottom of the case.  
  ![picot_o44_bg_assembly_1](/images/bg_assembly_1.jpg)

  Place the daughter board on top of the spacers and screw it in place with 3mm screws.  
  ![picot_o44_bg_assembly_2](/images/bg_assembly_2.jpg)

  Place picot5400 at the center.  
  ![picot_o44_bg_assembly_3](/images/bg_assembly_3.jpg)

  Place spacers on the four corners of the picot5400 and screw them in from the bottom with 5mm screws.  
  ![picot_o44_bg_assembly_4](/images/bg_assembly_4.jpg)

  Place the ball case base and secure with 5mm screws.  
  ![picot_o44_bg_assembly_5](/images/bg_assembly_5.jpg)

  Bend the flat cable and attach it to the picot5400 connector.  
  ![picot_o44_bg_assembly_6](/images/bg_assembly_6.jpg)  

  Connect the other end of the cable to the connector on the PCB.  
  ![picot_o44_bg_assembly_7](/images/bg_assembly_7.jpg)  

  Place the PCB into the case. If the silicone tubes get caught, gently push in.  
  ![picot_o44_bg_assembly_8](/images/bg_assembly_8.jpg)  

  Put ball and keycaps, and take a photo.  
  ![picot_o44_bg_assembly_9](/images/bg_assembly_9.jpg)  

### Firmware

  It is delivered with the default firmware is written. If you wish to write your own firmware, please follow the instructions below.

  - Press the RESET button while holding down the BOOT button on the picot5400 to enter boot loader mode.
  - The firmware is written by dragging and dropping the [.uf2](https://github.com/aki27kbd/picot_o44/blob/main/firmware/aki27_picot_o44_vial.uf2)file into the drive named RPI-RP2.  　

  Keymap is editable from [vial](https://vial.rocks/).  
  You can confirm that keys and trackball are working correctly with this firmware.

  The default firmware enables "Auto Mouse Layer", with which you can automatically jump into a specific mouse layer when you move trackball. You can toggle on/off this function with the custom keycode `AM_TOG`.

  The source code is available [here](https://github.com/aki27kbd/vial-qmk/tree/vial/keyboards/aki27/picot_o44).


## Custom Keycodes

  Several custom key codes can be set for trackball operation.

  Keycode   |Description
  ---------|-----------
  `CPI_SW`  |Change the CPI of the trackball. With the default firmware, each press changes the CPI in the following order: 200 -> 400 -> 800 -> 1600 -> 3200 -> 200....
  `SCRL_SW` |Changes the sensitivity of the sensor in scroll mode. The higher the value, the smaller the amount of scrolling.
  `ROT_R15` |Turns the Y axis of the mouse sensor 15 degrees clockwise.
  `ROT_L15` |Rotate the Y axis of the mouse sensor 15 degrees counterclockwise.
  `SCRL_MO` |	Enables scroll mode for as long as it is pressed.
  `SCRL_TO` |Toggles between scroll mode and mouse mode each time it is pressed.
  `SCRL_IN` |Inverts the scroll direction.
  `AM_TOG` |Toggle the function of auto mouse layer.

  Custom key codes can be set in vial using the custom key code under the User tab.  
  ![CustomKeycode_rev](/images/bg_customkeycode.jpg)



## Notes
If you have any problems, please contact us at[Twitter](https://twitter.com/aki27kbd).

Also, it would be very encouraging if you could upload the completed photos to social networking sites. (If you don't feel comfortable uploading your photos, you can send them directly to us via DM.)

The hashtag is #picot_o44.
