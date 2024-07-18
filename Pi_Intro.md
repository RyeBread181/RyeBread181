### Raspberry Pi intro Project
This is a organizaitonal document laying out the plans and documenting progress of my raspberry pi exploration project. This document should outline the project, goals, expected challenges and steps that I want to take with this project.

## Goals
The final product in mind is a robot arm with two segments capable of moving it's end effector to precise coordinates in a 2-dimentional plane.

The goal of this project is to gain knowledge and experiment with:
- Setting up a raspberry pi
- Establishing output and input signals to and from servo motors
- Using inverse kinematics to calculate joint angles from end effector locations.
- Design, model, and print structural components of the project.

# Steps

## Hardware
- Raspberry Pi 4B (4GB)
- Micro SD card (32GB)
- Adafruit Servo Hat for Raspberry Pi ([1528-1372-ND](https://www.digikey.ca/en/products/detail/adafruit-industries-llc/2327/5629420?utm_adgroup))
- 2x 5 volt, 2 amp, 2.1 mm DC power supply ([WSU050-2000](https://www.digikey.ca/en/products/detail/triad-magnetics/WSU050-2000/3094911))
- Jumper wires (male to female) ([]())_
- 2x Servo motors ([MG996R](https://www.amazon.ca/RGBZONE-MG996R-Torque-Digital-Helicopter/dp/B07RFRLRV8/?th=1))

## Dynamics (Torque Requirements)

The rated torque of the MG996R servo motor is 11 kg*cm.
The following dimensional relationships between different segments of the arm are as follows

Insert Figures

A = 4/3*B = 8/3*C
a = 4/3*b = 8/3*c c = 50g
x = 100g, y = 155g

t = 0.5Aa + Aw + (A+0.5*B)b + (A+B)u + (A+B+0.5C)c

solving for the length C, with the rated torque above, we get C = 6.13 cm, and thus B = 12.27 cm and A = 16 cm


By removing motor 3 (claw allignment) we can reduce the end effector weight (reducing u to 100g) and instead we can use the motor to aid in the base torque doubling it to 22 kg/cm.
This changes our maximum lengths to A = 38 cm, B = 28 cm, C = 14 cm.
