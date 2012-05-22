Dim Sum Labs Door Lock Project
==============================

Introduction
------------

Originally started by [Alex Hornstein](http://www.artiswrong.com),
code at
[github/enjrolas/OpenLock](https://github.com/enjrolas/OpenLock).

Extended by [Martin Dengler](http://www.martindengler.com) on
[github/dimsumlabs/doorlock](https://github.com/dimsumlabs/doorlock)
to be specific to [Dim Sum Labs in Hong Kong](http://dimsumlabs.com)
and updated for the new installation location.  We lose the generic
open door lock goal, and gain yet another working door lock example to
confuse others.  But it actually lets us in to our hacker space now.
Soon.


Overview
--------

Swipe your card and the door lock releases.  You get in and get on
with making.


    Power --------\
                   ---> Arduino ---> Electric lock /
    Ethernet -----/                  strike panel


Details
-------

Pinouts:

RFID sensor board                        Arduino

    J1 - Green            <----    ---->  D7
    J2 - Green & White    <----    ---->  D6
    J3 - Blue             <----RJ45---->  D5
    J4 - Blue & White     <----    ---->  D4
    J5 - Orange           <----    ---->  D3



Wiring:
                                                                   ||
                                                                  Door
                                                                   ||
  +12V                                                             ||
   |                                                               ||
   |----yellow-----------------------+---------+                   ||    +--------+
   |                                 |         |==------- RJ45 --------==| RFID   |
   |                                 | Arduino |==/                ||  \=| reader |
   `----red----->  +----+            |         |                   ||    +--------+
                   |Lock|            +---------+                   ||
                   +----+              |                           ||
                      |                |                           ||
                      |                |                           ||
                       \ -------       |                           ||
                        | Trans |-------                           ||
                        | istor |      |                           ||
                       / -------       Z                           ||
                      |                Z resistor                  ||
                      |                Z  Gray, Orange,            ||
                      |                |  Blue Brown               ||
    ------------------+----------------/                           ||
    |                                                              ||
    |                                                              ||
  -----                                                            ||
   ---                                                             ||
                                                                   ||
------------------------------------------------------------------------------------------


Transistor's markings:

    IRF644
    I[diode symbol]R 618P
    M4 [circled]4F HD



Proposed new inputs / outputs
-------------------------

Arduino connected to:

S1) "Door-closed" switch (NC)
S2) "Key-in-lock" switch (NO)
S3) "Deadbolt-home" switch (NC)
S4) "Knobbolt-home" switch (NC)
S5) "Lock opened" switch (NO)
