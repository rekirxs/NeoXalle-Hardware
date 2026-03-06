# NeoXalle-Hardware

Hardware side of the Neoxalle reaction training system.

This repository contains the electronics design and wiring references used to build the Neoxalle nodes. Each node acts as a standalone reaction target with lights, motion sensing, and vibration feedback. The goal of the project is to create something similar to BlazePods but open and customizable.



Each Neoxalle unit is built around an ESP32-C3 microcontroller. The device controls LEDs, reads motion sensors, and triggers vibration motors depending on what the software requests.

The nodes are meant to be used in reaction training games where users hit or move the device when it lights up.

Main functions:

LED feedback for visual signals
Impact detection using an accelerometer
Vibration motor for feedback
Battery powered operation
Communication with the Neoxalle app (another repository for that)

The hardware was designed to stay simple and inexpensive while still being responsive enough for sports training.

Hardware

Current prototype uses the following components:

ESP32-C3
MPU6050 accelerometer

WS2812b 24b / NeoPixel LED ring
Coin vibration motor
5V 1A battery charging module
3.7V 1200 mAh LiPo battery
12V - 5V step-down / voltage regulation
5V - 3.3V step-down / voltage regulation

Most of the components are easy to find on AliExpress or similar electronics suppliers.

Basic Architecture

Battery
→ Charging module
→ Voltage regulation
→ ESP32 + sensors + LEDs + motor

The ESP32 handles:

sensor reading
hit detection
LED control
game logic



Impact detection is intentionally simple for now: it mostly looks at sudden acceleration spikes from the top direction rather than full motion tracking.

Project Status

Still a prototype.

Things that work:
LED signaling
impact detection
vibration feedback
basic standalone reaction mode

Things still being improved:

sensor filtering
power efficiency
enclosure design
communication with the Neoxalle mobile app



Goal of the Project

The idea behind Neoxalle is to build a fully customizable reaction training system without being locked into expensive commercial hardware.
Commercial systems like BlazePods are great, but they are expensive and closed. This project tries to recreate similar functionality using open hardware so it can be modified, studied, and improved.

Notes

This is a personal project and the hardware design changes often as new versions are tested.
If something in the repo looks messy, it probably means it's still being experimented with.
