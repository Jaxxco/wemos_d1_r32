# wemos_d1_r32
**The Wemos D1 R32 board has a design flow. Usb powered the device may not boot.**

Powering the CH340C USB serial converter from 5V Vbus will output 5V on RX/TX pins. Check schematic (sch-Wemos-D1-R32.pdf) for reference.
The CH340 datasheet has specific instructions how to operate the serial converter from 3.3V only.
I made a few changes to the PCB to fix the problems found:

1. Cut the 5V Vbus trace powering the CH340
2. Add wire from 3.3V regulator output to pin 16 (VCC) and pin 4 (V3). Datasheet reference page 3: Connect to VCC when VCC is 3V3
3. Removed marked diode M7 (1N4007) and replaced with wire link to allow 5V input from DC-DC converter to 1117 3.3V regulator.
