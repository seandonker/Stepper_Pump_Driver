# Stepper Pump Driver
Kicad design files and C code (adding soon) for a small PCB to control a peristaltic stepper motor pump (or any single low current bipolar stepper really).

![Rendered_Board](https://github.com/seandonker/Stepper_Pump_Driver/assets/121892380/bc6d3e3b-a1cf-4df6-b510-54e2f7635402)

This project was created as a cheaper alternative for fully integrated peristaltic pump solutions that tend to cost $200 or more. These stand alone units use pumps that can be had for ~$50 and lack the full programmability that this project offers through Arduino coding. While this project was meant to be used for controllings pumps (like 
[this pump here](https://www.amazon.ca/Peristaltic-Stepper-Kamoer-KPHM400-Variable/dp/B097XXJ1XD/ref=sr_1_6?crid=3FM26AUWYPZCK&keywords=peristaltic+stepper&qid=1704066873&sprefix=%2Caps%2C176&sr=8-6)), it can be used for a variety of purposes where some adjustments need to be made on the fly by someone who may not know how to program/flash the arduino. This is why the design features a potentiometer and a button to change things like speed or on-time intervals. 

Component Requirements
---------------------
Apart from the provided (not yet provided) BOM from Digikey. The system needs a power supply, stepper motor, and the display purchased separately. 
* The power supply jack is a standard 2.1mmID x 5.5mmOD size and the supply should be rated for 12v and 3 amps or greater. 
* Bipolar stepper motor (currently selected plug socket is for a JST XHP-4 and max motor current is 1A RMS)
* The OLED display is a common 0.91" I2C with a SSD1306 chipset used in Arduino projects
* The USB differential lines were designed for a 1mm thick, 1oz top and bottom, 2-layer board (I ordered from JLPCB)

Programming and Power
---------------------
The board uses the common ATMEGA328P found in some standard models of Arduinos as this allows for the use of the libraries created for the OLED screen saving a lot of time and effort. 
There is an in-circuit-serial-programming (ICSP) header to burn the arduino bootloader if the chips were purchased blank from a distributor. Then you can either continue using the header for programming or use the USB port. For the USB to work however, the USB host controller chip (FT230X) needs to be programmed through the FT_PROG utility to change one output signal of the device. Please check the schematic and the datasheet of the chip for more details. The motor driver can only be powered from the 12v source but the MCU can run from either the USB or the 12v adapter allowing for programming without the 12v supply. Both can be plugged in simultaneously without issue for serial communication for data logging or other purposes. 

Future Improvements
------------------
I would like to use a 5v regulator capable of higher input voltages (or use a DC-DC converter) so the motor controller is capable of higher speeds. With that, it would be better if the PCB has 2oz copper layers for more current and better heat sinking capabilities. This would likely require a 4-layer board however as the USB trace impedance would become hard to design. A rotary encoder would be a much better method of input too, and would be easy to implement in hardware with a 4-layer board (but would require slightly more programming).

