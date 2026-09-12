<img width="1280" height="640" alt="git (1)" src="https://github.com/user-attachments/assets/8920b256-2ba8-4988-b824-5351134eb4bd" />



# [sukumarakurup] 🎯


## Basic Details
### Team Name: [last three brains]


### Team Members
- Team Lead: [abhishek p] - [govt engineering college kozhikode]
- Member 2: [sam yesudas] - [govt engineering college kozhikode]


### Project Description
**KURUP** is a 4-wheel autonomous robot inspired by the famous Sukumara Kurup story—because just like him, nobody can catch it! 😂 Built using an Arduino Uno, L298N motor driver, four geared motors, and an IR sensor, Kurup detects anyone approaching and quickly escapes by reversing, turning, and changing direction. The idea is simple: **if you try to catch Kurup, Kurup runs away!** 🏃‍♂️💨🤖


### The Problem (that doesn't exist)
People keep trying to catch autonomous robots. Why make it easy for them? 😎

### The Solution (that nobody asked for)
Meet KURUP — a robot that detects anyone coming near and immediately makes an escape. It reverses, turns, changes direction, and keeps running… because just like its namesake, Kurup isn't planning to get caught! 😂

## Technical Details
### Technologies/Components Used
For Software:
- [C/C++ (Arduino) — for programming the Arduino Uno and controlling the IR sensor and motors.]
- [Arduino Framework — used to program and control the Arduino Uno]
- [ No external libraries — the project uses only the built-in Arduino functions]
- [Arduino IDE — for writing, compiling, and uploading the code.
USB Cable — for programming the Arduino Uno.
Serial Monitor — for testing and monitoring the IR sensor.
Jumper Wires & Breadboard — for making and testing connections.]

For Hardware:
- [#
Component
Quantity
Purpose
1
Arduino UNO   1
L298N Motor Driver  Module      1
Controls the two DC motors     3
DC Geared Motors     2
Drives the robot       4
Robot chassis       1
Mechanical frame     5
Robot wheels     4
Connected to the motors      8

Supports the front/rear of chassis      2
IR Obstacle Detection Sensor       1
Battery holder      1

Breadboard
1
Prototyping connections
11
Jumper wires – Male-Male
Several
Arduino/breadboard connections
12
Jumper wires – Male-Female
Several
Sensor connections
13
Jumper wires – Female-Female
Several
Module connections, if required
14
USB cable for Arduino UNO
1

Main ON/OFF control
16
Motor mounting hardware
1 set
Screws/nuts/spacers
As required]
- [1. Component Specifications

Component	Specification	Qty.

Arduino UNO	ATmega328P, 5 V logic, 14 digital I/O, 6 PWM pins, 10-bit ADC -  1no.

IR Obstacle Sensor	3-pin digital IR sensor, 5 V supply, adjustable detection range, digital OUT	1no

L298N Motor Driver	Dual H-bridge, suitable for 2 DC motors, logic supply 5 V -- 1no
DC Geared Motors	3–6 V DC geared motors, approximately 100–300 RPM -- 2 no
Wheels	Compatible with geared motors, approximately 65–70 mm diameter -- 2
Caster Wheel	Free-rotating support wheel --1
Robot Chassis	Acrylic/wood/plastic, approximately 2-wheel-drive type --1
Battery Holder	2 × 18650 holder --1
18650 Batteries	Rechargeable Li-ion, preferably matched cells --2
Breadboard	400/830-point solderless breadboard --1
Jumper Wires	Male-Male, Male-Female and/or Female-Female --1 set
Power Switch	SPST ON/OFF switch --1
USB Cable	USB cable compatible with Arduino UNO -- 1


Recommended motor specification

For the chassis shown in your photo, something around:

3–6 V, 100–300 RPM geared DC motor

is a reasonable choice

Sensor Specification

IR obstacle sensor

Use a common module such as:

Operating voltage: 5 V

Output: Digital

Detection: IR reflection

Detection distance: typically ~2–30 cm, depending on module and adjustment

Adjustable sensitivity using onboard potentiometer

Pins: VCC, GND, OUT


Mount it at the front of the robot, facing forward.

OBJECT
                ↓
              🧱
                ↓
           ┌────────┐
           │ IR     │
           │ SENSOR │
           └───┬────┘
               ↓
        ┌──────────────┐
        │    ROBOT     │
        └──────────────┘
          O          O

When the object enters the sensor's detection range:

IR detects → Arduino receives signal → motors run backward → object gets farther → sensor stops detecting → robot stops.

]
- [
3. Tools Required

Basic assembly tools

Tool	Purpose

Screwdriver set	Mounting motors, chassis and modules
Wire stripper/cutter	Preparing jumper/power wires
Long-nose pliers	Handling wires and small components
Allen key set	Motor/wheel mounting if required
Electrical tape	Insulation and wire management
Cable ties	Organizing wires


Electronics tools
Tool	Purpose

Digital multimeter	Checking voltage, continuity and wiring
Soldering iron	Permanent connections
Solder wire	Soldering connections
Desoldering pump/wick	Correcting soldering mistakes
Heat-shrink tubing	Insulating permanent connections
DC power supply/battery charger	Testing/powering the circuit


Programming tools

You need:

Computer/laptop

Arduino IDE

USB cable

Arduino UNO board]

### Implementation
For Software: arduino ide, c++,
for hardware :arduino uno , ir sensor , motor driver, dc gear motors, 


# Run
power on the car,arduino boots up and starts to function. car moves away as person approches

### Project Documentation

# Screenshots (Add at least 3)
<img src="Screenshot 2026-09-12 064847.png">

<img src="Screenshot 2026-09-12 064917.png">

<img src="Screenshot 2026-09-12 065009.png">

# Diagrams
                 ┌───────────────────┐
                 │      POWER ON     │
                 └─────────┬─────────┘
                           ↓
                 ┌───────────────────┐
                 │  Initialize       │
                 │ Arduino + IR +    │
                 │ Motor Driver      │
                 └─────────┬─────────┘
                           ↓
                 ┌───────────────────┐
                 │ Read IR Sensor    │
                 └─────────┬─────────┘
                           ↓
                  ┌────────────────┐
                  │ Object/Hand    │
                  │ Detected?      │
                  └───────┬────────┘
                      YES │       │ NO
                          ↓       ↓
                ┌─────────────┐  ┌─────────────┐
                │    STOP     │  │ Move Forward│
                │   Motors    │  │  All Motors │
                └──────┬──────┘  └──────┬──────┘
                       ↓                 │
                ┌─────────────┐          │
                │ Move         │          │
                │ Backward     │          │
                └──────┬──────┘          │
                       ↓                 │
                ┌─────────────┐          │
                │ Turn Left /  │          │
                │ Right        │          │
                └──────┬──────┘          │
                       ↓                 │
                ┌─────────────┐          │
                │ Move Forward│◄─────────┘
                └──────┬──────┘
                       ↓
                 ┌─────────────┐
                 │ Read IR     │
                 │ Again       │
                 └──────┬──────┘
                        │
                        └───────────↺

For Hardware:

# Schematic & Circuit
                         ┌─────────────────┐
                         │    IR SENSOR    │
                         │                 │
                         │ VCC ────── 5V   │
                         │ GND ────── GND  │
                         │ OUT ────── D2   │
                         └────────┬────────┘
                                  │
                                  ↓
                         ┌─────────────────┐
                         │   ARDUINO UNO   │
                         │                 │
                         │ D2  ← IR OUT    │
                         │ D5  ── ENA      │
                         │ D6  ── ENB      │
                         │ D8  ── IN1      │
                         │ D9  ── IN2      │
                         │ D10 ── IN3      │
                         │ D11 ── IN4      │
                         │ GND ────────────┼──────┐
                         └────────┬────────┘      │
                                  │               │
                                  ↓               │
                         ┌─────────────────┐      │
                         │      L298N      │      │
                         │  MOTOR DRIVER   │      │
                         │                 │      │
                         │ ENA  ← D5       │      │
                         │ ENB  ← D6       │      │
                         │ IN1  ← D8       │      │
                         │ IN2  ← D9       │      │
                         │ IN3  ← D10      │      │
                         │ IN4  ← D11      │      │
                         │                 │      │
                         │ OUT1 ──┐        │      │
                         │ OUT2 ──┼── LEFT  │      │
                         │        │  MOTORS │      │
                         │ OUT3 ──┐│        │      │
                         │ OUT4 ──┼┼ RIGHT  │      │
                         │        ││ MOTORS  │      │
                         │ GND ───┼─────────┼──────┘
                         │ VS/+12V│
                         └────┬───┘
                              │
                              │
                       ┌──────┴──────┐
                       │   BATTERY   │
                       │             │
                       │ + ──→ VS    │
                       │ - ──→ GND   │
                       └─────────────┘

motor arrangement
                    FRONT
              ┌───────────────┐
              │               │
        M1 ●──│               │──● M2
              │    KURUP      │
        M3 ●──│               │──● M4
              │               │
              └───────────────┘
                    REAR

       M1 + M3 → L298N OUT1 / OUT2
       M2 + M4 → L298N OUT3 / OUT4



### Project Demo
# Video
https://drive.google.com/file/d/1AwqczFFr3g0qBv-TVHzmjC8m3YR8cFrb/view?usp=sharing

# Additional Demos
[[Add any extra demo materials/links]](https://drive.google.com/file/d/1Z-21T7V9XI_eBu22mCNq7mb8NxkbH935/view?usp=drivesdk)

## Team Contributions
- Sam Yesudas: project design,circuit design
- Abhishek p: hardware interface and assembly


---
Made with ❤️ at TinkerHub Useless Projects 

![Static Badge](https://img.shields.io/badge/TinkerHub-24?color=%23000000&link=https%3A%2F%2Fwww.tinkerhub.org%2F)
![Static Badge](https://img.shields.io/badge/UselessProjects--26-26?link=https%3A%2F%2Ftinkerhub.org%2Fevents%2F1M8ORET9A1%2Fuseless-projects-3.0)



