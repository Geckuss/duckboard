Original repositories:
https://github.com/doodboard/tutorial/tree/main
https://github.com/doodboard/source-code

Founder of duckboard has been offline since 2021

# Build guide for duckboard

Here is a comprehensive build guide for duckboard
<br/>

## Table of Contents

* [prerequisites](#prerequisites)
* [components](#components)
* [flashing](#flashing)
* [LEDs](#leds)
* [diodes](#diodes)
* [hotswap sockets](#hotswap-sockets)
* [ProMicro](#promicro)
* [rotary encoder](#rotary-encoder)
* [top plate](#top-plate)
* [OLED](#oled)
* [assembly](#final-assembly)

You may also want to read the [FAQs](faqs.md).

<br/>

## prerequisites

There are some items you will need in order to build your duckboard.

### Required

* A [soldering iron](https://en.wikipedia.org/wiki/Soldering_iron) that can operate at or below 300° Celsius (572° Fahrenheit).
* [Solder](https://en.wikipedia.org/wiki/Solder) to join the components to the PCB. The type of solder depends on your preference.
* A small [Phillips](https://en.wikipedia.org/wiki/List_of_screw_drives#Phillips) screwdriver. Size 1 works, as does size 0.
* A willingness to do some soldering and assemble a duckboard!

### Optional but highly recommended

* [Tweezers](https://en.wikipedia.org/wiki/Tweezers) for gripping the small components.
* Some kind of desoldering tool, such as a solder wick (aka desoldering braid) or solder sucker (aka desoldering pump). This will be extremely helpful in case you make small mistakes along the way. Check out the tools in [this Wikipedia article](https://en.wikipedia.org/wiki/Desoldering#Tools) for more information.
* [Flux](https://en.wikipedia.org/wiki/Flux_(metallurgy)#Soldering) for certain techniques and making your job easier.
* [Wire cutters](https://en.wikipedia.org/wiki/Diagonal_pliers) that are flush-cutting. Flush-cutting is preferred as this will make it easier to get the cuts you need.

### Optional

* If you want to customize the firmware, you will likely need to learn more about QMK. Please check out the [QMK documentation](https://docs.qmk.fm/) as that is out of scope of this tutorial.
* If you are newer to soldering, you may want to check out a guide like the [Adafruit Guide To Excellent Soldering](https://learn.adafruit.com/adafruit-guide-excellent-soldering). This will help create [good solder joints](https://learn.adafruit.com/adafruit-guide-excellent-soldering/making-a-good-solder-joint) and identify and address [common soldering problems](https://learn.adafruit.com/adafruit-guide-excellent-soldering/common-problems).

<br />
<br />

## components

### A single duckboard kit includes the following:

![component_1](https://github.com/Geckuss/duckboard/assets/58637152/6567cbcd-49ef-4ffd-aa6f-1fd2a886fbca)


| Label  | Part name         | Part quantity | Possible replacement (if needed)  |
|--------|-------------------|---------------|-----------------------------------|
| **a**  | Diode             | 22            | 1N4148 THT Diode                  |
| **b**  | M2 16mm bolts     | 4             |                                   |
| **b**  | M2 nuts           | 4             |                                   |
| **b**  | Short standoffs   | 4             | h: 4mm                            |
| **b**  | Long standoffs    | 4             | h: 6mm                            |
| **c**  | LEDs              | 8             | SK6812 3535 Mini 		 |
| **d**  | Hotswap sockets   | 21            | Kailh hotswap sockets             |
| &nbsp; |                   |               |                                   |
| **e**  | Encoder knob      | 1             |                                   |
| **f**  | Rotary encoder    | 1             | EC-11 Encoder                     |
| &nbsp; |                   |               |                                   |
| **g**  | Top plate         | 1             |                                   |
| **h**  | PCB               | 1             |                                   |
| **i**  | Bottom plate      | 1             |                                   |
| &nbsp; |                   |               |                                   |
| **j**  | Pro Micro         | 1             |                                   |
| **k**  | OLED              | 1             | .91” 128px x 32px OLED 		 |

<br/>
<br/>

### A single acrylics case kit includes the following:

![component_2](https://github.com/Geckuss/duckboard/assets/58637152/139b00e5-126e-4c68-b2af-049b3b5b5564)

| Label  | Part name                       | Part quantity |
|--------|---------------------------------|---------------|
| **l**  | Acrylics top plate              | 1             |
| **m**  | Acrylics plate                  | 1             |
| **n**  | Acrylics boundary (small holes) | 1             |
| **o**  | Acrylics boundary (big holes)   | 1             |
| **p**  | Acrylics bottom plate           | 1             |

<br/>
<br/>

![component_3](https://github.com/Geckuss/duckboard/assets/58637152/480994e8-2c60-47b1-a3af-f67b7e0671a2)

| Label  | Part name         | Part quantity |
|--------|-------------------|---------------|
| **q**  | M3 16mm bolt      | 4             |
| **r**  | M3 insert nuts    | 4             |

<br/>
<br/>

## flashing

### Please flash and test your promicro before starting the build!

You can download the **hex file** for duckboard from this repository

If you wish to compile your own hex file, you can grab the **source code** from this repository

You can grab **QMK toolbox** from [**here**](https://github.com/qmk/qmk_toolbox)

If you wish to use VIA, download the **hex file** for duckboard from this repository

![qmk_toolbox_1 (1)](https://github.com/Geckuss/duckboard/assets/58637152/e9cad255-4c7a-44e2-8e5a-266fa9ca798e)


1. confirm you have downloaded and opened the **right HEX file** on qmk toolbox
2. MCU should be set to **"atmega32u4"**
3. check **Auto-Flash**

<br/>

Plug in your pro micro, and if it doesn't flash automatically, **short GND to RST on pro micro twice, fast.**<br/>
Use a **tweezer** or **pliers** or anything else conductive.

You should see the following if everything went successfully.

![qmk_toolbox_2](https://github.com/Geckuss/duckboard/assets/58637152/c5fbbf2e-2565-42dc-b319-b6d3c987dbca)

<br/>
<br/>

## LEDs 

### Now we'll work on the LEDs. This is the *toughest* part of the build. 

The LEDs are SMD, meaning they are surface mounted as opposed to through hole mounted. 
Therefore, using **flux is highly recommended** as it helps solder to flow under the LEDs far more easily.
I personally prefer flux paste, as opposed to flux pens, but it's up to personal preference.

LEDs provide underglow to the duckboard. If you find it too frustrating, it's **alright** to forego the LEDs. <br/>
**It won't affect the core functionality of duckboard as a macropad**

![LED_1 (1)](https://github.com/Geckuss/duckboard/assets/58637152/ea5551e9-5cca-4873-9666-964541a33d32)

LEDs should be positioned as shown above, **the small black square inside the LED should line up with the small circle on the PCB**.

<br/>

[**This**](https://streamable.com/dimwli) is how I solder the LEDs.
1. apply flux to **both** the PCB and the LED with a brush
2. set the soldering iron to **300C** to prevent burning out the LEDs
3. place LED on the PCB. Make sure it's positioned** correctly** on the pads.
4. apply a **small** amount of solder to the soldering iron
5. make a short swiping motion **perpendicular** to the LED
6. repeat for all **4** pads.

<br/>

![LED_3](https://github.com/Geckuss/duckboard/assets/58637152/81d64a84-f901-413d-be3e-6a6351f44418)

The finished solder joints should look like the photo above. You are aiming for the **nice slope of solder**, not a blob.
Please make sure you only make contact with the iron for **2-3 seconds** at a time. Longer exposure to heat can burn out the LED.

In the case that you burn through even the extra LEDs provided, model number is **SK6812 3535 mini**.

<br/>
<br/>

## diodes

### Next step is installing the diodes. 

![diodes](https://github.com/Geckuss/duckboard/assets/58637152/6b526182-6025-456c-a930-949c4dc9c2bc)

Nothing fancy here. **Align the diodes as shown above**, and solder them in. I recommend using flux, but it's not required.
There are total of **22** diodes to install: 21 for the 21 switches, and 1 for the push function of rotary encoder.

If you plan to use stabilizers, pay extra attention to the diodes near stab housings. 
You should** clip the diode legs flush to the PCB** in order to prevent clearing issue. 

Here is an up-close image of what a soldered diode looks like:

![diode_soldered](https://github.com/Geckuss/duckboard/assets/58637152/50059f17-29fa-41a8-8a86-72a1d39fd1e8)

<br/>
<br/>

## hotswap sockets

### And now onto the hotswap sockets.

![hotswap_1](https://github.com/Geckuss/duckboard/assets/58637152/f8ef6358-7f50-4697-ac38-feb4f4945649)

Again, nothing fancy here. Place the hotswap sockets into the PCB, following the guidelines. <br/>
If you prefer to solder your switches directly to the PCB, you can skip this process, and solder in the switches later **after** installing the top plate. <br/>
Depending on if you would like to use duckboard as **full 1u macropad**, or as **standard numpad**, you should solder your hotswap sockets **accordingly**.

Here is an up-close image of what a soldered hotswap socket looks like:

![hotswap_soldered](https://github.com/Geckuss/duckboard/assets/58637152/d771ad85-7baa-4ce0-b7ae-a689d8d82c72)


<br/>
<br/>

## ProMicro

### Now the real fun begins.

![promicro_0](https://github.com/Geckuss/duckboard/assets/58637152/0584521d-cee5-4965-ac1d-6f278f4e5b16)

Again, I recommend using flux, but it's not required. Just makes your life a **little** easier.

a) Solder the legs to ProMicro. Note the **longer side of the legs goes into the PCB** <br/> 
b) Solder the ProMicro to the PCB, and cut off the pins as much as you can, **without** damaging your solder joints.

After soldering and trimming the pins, your Pro Micro should be attached to your PCB similar to this:

![promicro_soldered](https://github.com/Geckuss/duckboard/assets/58637152/61715cbc-02a1-4c26-aa8a-5d11c85b8d71)

<br/>
<br/>

### Now is the time to verify your soldering skills. 
Plug in your duckboard to your PC via **MicroUSB** cable.
All **8** LEDs should light up by default. If only a few of them lights up, follow these steps:

Start working from **LED_1**. The signal line for LEDs are connected in **serial** to help you debugging.
For example, if none of your LEDs light up, try reflowing LED_1. 
If LED_1, 2 and 3 light up, but not 4, try reflowing LED_3 and 4 until 4 lights up.

Default colour for LED is **RED** with default R2/R3 hex file. If some of your LEDs light up in different colour, it's due to **corrupted** signal caused by bad solder joints.
If some of your LEDs work, but not in serial, so for instance LED_1, 2 and 8 light up, the same principle applies. Work on LED 2 and 3 until 3 lights up.

![promicro_2](https://github.com/Geckuss/duckboard/assets/58637152/b4097912-5044-4a4b-a0bc-df4a52e300c5)

This is the schematic of the LED wiring for reference.

<br/>

![hotswap_2](https://github.com/Geckuss/duckboard/assets/58637152/c48cc929-e605-4baa-92dd-e7cd98597b0e)

This is also the perfect time to test your **keypresses**. You can either plug in the switches to test the keystrokes, or manually short the hotswap sockets. 

Default hex file for R2/R3 has OLED enabled. ProMicro awaits return signal from OLED.
So until the display is installed, keypresses will be **delayed**, and you'll have to hold down each keypress a little bit longer for it to register.

To test without installing switches, short the **blue** circles if you have the **hotswap sockets** installed. Short the **yello** circles if you plan to solder the switches in **directly**.

<br/>

![good soldering](https://cdn-learn.adafruit.com/assets/assets/000/001/978/large1024/tools_Header_Joints.jpg?1396777967)
If you have any issues, first make sure your LEDs and diodes are **oriented right**, then **check** your soldering joints to see if they all look OK.
Here is a reference image in courtesy of **adafruit**. 

<br/>
<br/>

## rotary encoder

### Fun fun fun!

![encoder_1](https://github.com/Geckuss/duckboard/assets/58637152/496f9e81-0b16-45c2-955e-6c821a0db5f7)

No fancy tricks. Solder **7** spots circled above. Make sure the encoder is sitting **flush** to the PCB before you solder it.
The two tabs in the middle are for **structural** purposes only. Apply solder generally. 
The thinner legs to the top and bottom are **malleable**. Bend them a little if they need to be in order to fit the PCB.

You can also install the encoder knob now. **Align** the small screw to the flat face of encoder shaft. Screw it in for stability.

Plug in the USB cable, and test rotation in both directions, and pressing the encoder shaft in. 
It should **increase/decrease** the volume, and **mute/unmute** your media player.

<br/>
<br/>


## top plate

### Almost time to wrap it all up!

#### IF YOU WANT TO INSTALL ACRYLICS CASE, STOP AND CLICK BELOW


<details>
	<summary>CLICK ME</summary>
<br/>

![topplate](https://github.com/Geckuss/duckboard/assets/58637152/61704d5b-4d00-4186-8bed-fa185d5a0b13)

**Install stabilizers now** before moving on if you wish to use them. For 2u switches, I personally prefer the tactility of not having stabs installed, but that's just my personal opinion.

Grab the acrylics plate labelled "l" and "m" above, and gauge where the OLED needs to be. Solder the OLED in place. 

Then insert 4 x popnuts to the bottom 2 plates. Be **gentle**. If too tight, push it in with a hot soldering iron. Do not apply excessive force or the plate might crack.

Place the plate "m" on top of PCB. Slide the plate over the encoder. Note there is a **small metal tab** on the encoder. Manoeuvre around it. 

If you just can't fit the plate over the metal tab, take a **clean** soldering iron to the area of acrylic plate in contact with the metal tab, and gently push it. 

Your aim is to cleanly create a small gap for the metal tab to pass through.

Install your switches. The PCB is held in place by the hotswap sockets and the switches. The force of pressing the switches are transferred directly to the acrylic case.

Assemble with the rest of your acrylic plates and screw them in place. That's it, your are **done**. Install keycaps to your liking and type away!

-------------------------------------------------------------------------------------------------

</details>

![topplate](https://github.com/Geckuss/duckboard/assets/58637152/9609473b-130a-4e4c-a97d-f33bba6880b8)

**Install stabilizers now** before moving on if you wish to use them. For 2u switches, I personally prefer the tactility of not having stabs installed, but that's just my personal opinion.
Place the 4 screws into the plate, and screw in the **shorter** standoffs. Then place the top plate onto the PCB, and screw in the **longer** standoffs.
You may find it easier to hold the standoffs with **pliers** while screwing them in place.


<br/>
<br/>

## OLED

### 4 last solder joints

![oled_1](https://github.com/Geckuss/duckboard/assets/58637152/5112c239-9f86-480b-8b64-ce710fb7bfce)
**Remove the black plastic** from the OLED pins. Pull them out **gently** using your fingers or pliers if necessary.

![oled_2](https://github.com/Geckuss/duckboard/assets/58637152/ec3a1805-84f2-480f-a507-c75cda4fd655)
Install the OLED in place. Make sure the OLED module is **parallel** to the top plate, and is **positioned correctly** before soldering into place.

Plug in the USB cable once again at this point and ensure **everything** checks out. If you chose to solder the switchs in directly, now is the time to do so.

<br/>
<br/>

## final assembly

### FINISHED

![finished_1](https://github.com/Geckuss/duckboard/assets/58637152/7912e50e-4929-4403-bc96-cbe2336feedf)

Place the bottom plate in position and screw in the 4 x M2 nuts to finish off the build. **Install switches and keycaps to your liking, and type away**!

Here is the default **keymap** for reference. 
![keymap](https://github.com/Geckuss/duckboard/assets/58637152/6a45cd71-8e4a-43ca-92d5-553ff8b2737b)

Here is the pinout diagram for troubleshooting. 
![pinout_1](https://github.com/Geckuss/duckboard/assets/58637152/a3d56366-094c-46da-a417-1a6cb568bb54)


<br/><br/>

## what's next?

You can add your favourite stabilizers, switches, and keycaps! If you are interested in changing the default keymap or other functionality of the board, you may also want to learn about [QMK](https://docs.qmk.fm/) and use the duckboard source code
