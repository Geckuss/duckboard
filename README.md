# DDBD

This is a repository for source code and documentation of duckboard R2 assembly


To make your own firmware, or edit the preexisting one, you’ll need to have a code environment set up. Follow the QMK getting started doc here: https://beta.docs.qmk.fm/tutorial/newbs_getting_started
The basic applications you’ll need installed are: Python, MSYS, and a text editor of your choosing. VIA and QMK Configurator DO NOT WORK. OLEDs don’t play nice with either of the programs.

In order to change the animation, you’re gonna need to turn a B/W image into a string of numbers in this QMK logo editor:
https://joric.github.io/qle/
Edit it in keymap.c, and keep in mind the stock duck is 32x32 pixels and has 2 images. 

Reset the board by shorting GND & RST pins


Duckboard partslist:

Duckboard PCB
LED : SK6812 3535 Mini
Diode: 1N4148 THT Diode
Encoder: EC-11 Encoder 
OLED: .91” 128px x 32px OLED 
Hotswap sockets: Kailh hotswap sockets
M2 Screws 
M2 nuts
Standoffs
