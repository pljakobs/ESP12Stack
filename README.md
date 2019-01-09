# ESP12Stack
### An ESP12 Platform, adhering to the 30x30mm breakout boards often found but much more functional.
I have tested it with:
- ESPEasy
- SONOFF-TASMOTA
- Micropython
- Arduino
### Hardware
At this point, there is the base board which has:
- an ESP12 with all GPIO Pins brought to 2.54mm pin headers along the edge
- four WS2812B RGB or SK6812 RGBW individually addressable LEDs, which can be configured to be driven by various GPIO pins using 470Ohm resistors:
  - J02 -> GPIO2
  - J04 -> GPIO4
  - J05 -> GPIO5
  - J12 -> GPIO12
  - J13 -> GPIO13
only one of those should be installed at any given time
- low drop 3.3V regulator, the system can be powered either via the on-board USB connector or the 5V Vcc pin. Since there's no protection and those two 5V supplies form just one net, I suggest never to use both at the same time to avoid damage to your USB power source
- miniature switches for GPIO0 (FLASH) and RESET
- all necessary pull up / pull down resistors to be working as a stand alone device

In the FTDI vesion (currently untested) I have added an FTDI232 chip which should make the whole device in-place programmable, so no external USB-UART adapter is needed. Just plug it in to your PCs USB and you can talk to the ESP's UART
### There are a few other boards as well
- a 12-36V Switching Power Supply board that provides 5V (provided the feedback resistors are set correctly) to power the stack in an environment that requires those power levels (like a car)
- a five channel MOSFET board that can drive common anode LED strips
- an "experimentation" board that only has the VCC and GND pins pulled out to the outer row of mounting holes and otherwise offers as much of a "standard" layout board as possible for your own devices
### What I'm, working on:
the next board to come should be a display that just plugs on top of the base board, offering 240x240px through I2C
