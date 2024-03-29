Software to control 7-segment displays.

# Software:
Based on code found in the comments section of the [SparkFun Hookup Guide](https://learn.sparkfun.com/tutorials/large-digit-driver-hookup-guide/discuss). Thanks to [Member #910971](https://www.sparkfun.com/users/910971) and [Member #642108](https://www.sparkfun.com/users/642108).

This code is further improved to easily support multiple displays, as well as text/numbers, with scrolling.

# Hardware:
Tested with the following hardware:
* [7-Segment Display - 6.5" (Red)](https://www.sparkfun.com/products/8530)
* [SparkFun Large Digit Driver](https://www.sparkfun.com/products/13279)
* [RaspberryPi 4](https://www.raspberrypi.org/products/raspberry-pi-4-model-b/)
* [SN74AHCT125N Quadruple Bus Buffer Gates With 3-State Outputs](https://www.ti.com/store/ti/en/p/product/?p=SN74AHCT125N)
* [Adafruit Perma-Proto HAT](https://www.adafruit.com/product/2310)

It is likely to work with other variants, home made displays and/or drivers based on [TPIC6C596](http://www.ti.com/lit/pdf/slis093), as well as other voltage converters for signal, for example the [SparkFun Logic Level Converter](https://www.sparkfun.com/products/12009).

12v power to the displays are provided externally.

## Build instructions:
https://learn.sparkfun.com/tutorials/large-digit-driver-hookup-guide/all

In our case, we swapped the Arduino with a RaspberryPi 4. As the Pi operates with 3.3v signals on the GPIO compared to the 5v of the Arduino, the signal lines (clk, latch, data) needs to be adjusted via a logic level converter.

# Defaults:
Segments class parameters, based on the [Raspberry BCM pinout](https://pinout.xyz/):
* bcm_gpio_clock=11 *(CLK)*
* bcm_gpio_latch=13 *(Signals when to switch to the next display)*
* bcm_gpio_data=14  *(TXD - used to turn each segment on/off)*
* num_displays=7 *(The number of displays you've chained)*
* debug=False *(Turns on debug output to console)*
* offline=False *(Deactivates the actual GPIO-parts, used mainly for dev/tests)*
