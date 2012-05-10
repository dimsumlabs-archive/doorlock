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

RFID sensor board pinout:

    J1 - Green
    J2 - Green & White
    J3 - Blue
    J4 - Blue & White
    J5 - Orange


Wiring:


Current state of affairs: needs rewiring:

    Lock ----red----> cut
      |
      | yellow
      |            ,----------------\
      |   cut <-------=+-----+      |
      |                | Tra |      Z
      `---------------=| nsi |      Z resistor - Gray Orange Blue Brown
                       | str |      Z
          cut <-------=+-----+      |
                  `-----------------/


    Power --------red--------------------> cut
      |
      `--------yellow-----junction-------> cut
                             `-----------> cut


Transistor's markings:

    IRF644
    I[diode symbol]R 618P
    M4 [circled]4F HD
