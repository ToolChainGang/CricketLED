# CricketLED
Simple arduino driver for the "Handy Cricket" LED display

# About

The "Handy Cricket" is a robotics package, featuring a bespoke 4-digit LED display:

<img src="http://www.handyboard.com/cricket/bus/4digit/4dkb-sm.jpg" width="50%">

This project contains an arduino driver for the cricket bus, and a test program for the cricket LED display.

The test program can be used to test the features of your cricket LED display, and serves as a boilerplate
for calling the display functions.

<hr width="100%">

# CrucketBus.c, CricketBus.h

```C
//      //////////////////////////////////////
//      //
//      // In CricketBus.h
//      //
//      #define CRICKET_PORT                D
//      #define CRICKET_BIT                 7
//
//      //////////////////////////////////////
//      //
//      // In main.c
//      //
//      CricketBusInit();                   // Called once at startup
//
//      CricketBusPut(0x100,true);          // Send 0x100 as command to cricket bus
//      CricketBusPut(0x203,false);         // Send 0x203 as data (ie - not command) to bus
//
//      //////////////////////////////////////
//      //
//      // Cricket LED specific calls
//      //
//      In the calls below, ID can be zero (for "any"), or 1 or 2 to identify
//        which of two LED displays are connected. See Cricket LED display documentation for
//        how to set the device ID (involves cutting a trace on the board).
//
//      CricketLEDDec(1025,ID)              // Display numeric "1025" on LED display
//      CricketLEDHex(0x1025,ID)            // Display numeric "1025" on LED display
//      CricketLEDBright(7,ID)              // Set brightness level to 7
//
//      CricketLEDPat(a,b,c,d,ID)           // Set segments based on pattern (see notes below)
```

<hr width="100%">

# Running the test code

Connect the white, "bus signal" of your cricket display to PORTD.7
(Also Black GND to ground, and red BUSV to +5V)

Compile, load, and run this module.

Cricket display will begin a demo program:

    1) display a count in decimal
    2) display a count in hex
    3) cycle the display brightness
    4) cycle the digit segments
    5) repeat...

You can easily change the demo behaviour below.

The port and pin can be easily changed, see CrucketBus.h

