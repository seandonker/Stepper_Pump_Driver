# Stepper Pump Driver
Kicad design files and C code for a small PCB to control a peristaltic stepper motor pump (or any single low current bipolar stepper really).

![Rendered_Board](https://github.com/seandonker/Stepper_Pump_Driver/assets/121892380/bc6d3e3b-a1cf-4df6-b510-54e2f7635402)

This project was created as a cheaper alternative for fully integrated peristaltic pump solutions that tend to cost $200 or more. These stand alone units use pumps that can be had for ~$50 and lack the full programmability that this project offers through Arduino codeing. While this project was meant to be used for controllings pumps (like 
[this pump here](https://www.amazon.ca/Peristaltic-Stepper-Kamoer-KPHM400-Variable/dp/B097XXJ1XD/ref=sr_1_6?crid=3FM26AUWYPZCK&keywords=peristaltic+stepper&qid=1704066873&sprefix=%2Caps%2C176&sr=8-6)), it can be used for a variety of puposes where some adjustments need to be made on the fly by someone who may not know how to program/flash the arduino. This is why the design features a poteintiometer and a button to change things like speed or on-time intervals. 

Component Requirments
---------------------
Appart from the provided (not uet provided) BOM from Digikey. The system needs a power supply, stepper motor, and the display purchased seperatly. 
* The power supply jack is a standard 2.1mmID x 5.5mmOD size and the supply shoud be rated for 12v and 3 amps or greater. 
* Bipolar stepper motor (currently selected plug socket is for a JST XHP-4 and max motor current is 1A RMS)
* The OLED display is a common 0.91" I2C with a SSD1306 chipset used in Arduino projects

