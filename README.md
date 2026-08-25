# ROVE

### Remote Operated Vehicle Explorer

ROVE is a small phone-controlled rover built as the first physical prototype for a larger trekking project.

The goal of ROVE is simple: control a small rover from a phone while giving it basic obstacle avoidance so it doesn't blindly drive into things.

## Features

- 📱 Phone-controlled movement
- 🛞 4WD drive system
- 📡 HC-SR04 ultrasonic obstacle detection
- ⚡ Variable motor speed
- 🔌 USB serial communication
- 🧠 Arduino-based motor and sensor control
- 🛑 Automatic stop when an obstacle is detected

## How It Works

The phone acts as the controller and communicates with the Arduino through USB serial.

The Arduino receives movement commands and controls the motors through the L298N motor driver.

The HC-SR04 is connected directly to the Arduino. Before moving forward, the Arduino checks the distance in front of the rover. If an obstacle is closer than the configured safe distance, the rover stops.

## Components

- Arduino Uno R3
- L298N motor driver
- 2WD chassis
- 4 DC motors
- HC-SR04 ultrasonic sensor
- Phone
- USB cable
- Power bank
- Jumper wires

## Pinout

| Arduino Pin | Component |
|---|---|
| D5 | L298N ENA |
| D6 | L298N ENB |
| D8 | L298N IN1 |
| D9 | L298N IN2 |
| D10 | L298N IN3 |
| D11 | L298N IN4 |
| D2 | HC-SR04 TRIG |
| D3 | HC-SR04 ECHO |

D7 is currently unemployed.

## Phone Commands

The Arduino accepts simple serial commands:

| Command | Action |
|---|---|
| `F` | Forward |
| `B` | Backward |
| `L` | Left |
| `R` | Right |
| `S` | Stop |
| `+` | Increase speed |
| `-` | Decrease speed |
| `D` | Request distance |

## Obstacle Avoidance

The HC-SR04 provides distance information when the rover is commanded to move forward.

If the measured distance is below the configured safe distance, the Arduino stops the motors.

Obstacle detection is handled directly by the Arduino, so the rover can react without relying on the phone.


## Software

The rover is programmed using the Arduino IDE.

The Arduino handles:

- Motor direction
- Motor speed using PWM
- Serial commands
- Ultrasonic distance measurement
- Forward obstacle detection

The phone side will be developed separately as a controller interface.

## Project Structure

```text
ROVE/
├── README.md
├── JOURNAL.md
├── wiring-diagram.png
└── rover/
    └── rover.ino
