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

## Bill of the MAterials

| Component | Qty | Approx. Price (INR) | Approx. USD |
|---|---:|---:|---:|
| Arduino UNO R3 | 1 | ₹499 | $5.67 |
| L298N Motor Driver | 1 | ₹131 | $1.49 |
| TT Geared DC Motors | 4 | ₹90 each | $4.09 |
| Robot Chassis | 1 | ₹500 | $5.68 |
| HC-SR04 Ultrasonic Sensor | 1 | ₹61 | $0.69 |
| Jumper Wires | 1 set | ₹100 | $1.14 |
| Breadboard | 1 | ₹80 | $0.91 |
| USB Cable | 1 | ₹100 | $1.14 |
| Power Bank / Battery | 1 | ₹400 | $4.55 |
| **Estimated Total** | | **₹2,831** | **~$32.17** |

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

## 🔧 Hardware Design

The circuit was designed and tested online before being assembled physically.

<img width="3840" height="2160" alt="IMG_20260823_223311_281" src="https://github.com/user-attachments/assets/ca39238a-711d-432f-b69a-0719e8af32e6" />


## Project Structure

```text
ROVE/
├── README.md
├── JOURNAL.md
├── wiring-diagram.png
└── rover/
    └── rover.ino
