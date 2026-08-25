---

title: "ROVE"
author: "Akshat Jain"
description: "A phone-controlled Arduino rover with ultrasonic obstacle detection."
created_at: "2026-08-20"
------------------------

# August 20: Planning

I started with the idea of making a small rover that I could control from my phone. I wanted to keep the build simple and use the Arduino for the actual control instead of putting everything on the phone.

The parts I planned around were an Arduino Uno, L298N motor driver, four DC motors and an HC-SR04 ultrasonic sensor. The phone would communicate with the Arduino over USB serial.

The main controls I planned were forward, backward, left, right and stop, with the ultrasonic sensor being used to stop the rover if something was too close in front.

<img width="1561" height="932" alt="image" src="https://github.com/user-attachments/assets/916af166-2ac8-405b-98ed-bf536f72e73d" />


**Total time spent: 1.5 hours**

# August 20: Circuit Online

I made the circuit online before building it physically so I could work out the connections first.

The L298N handles the four motors. D5 and D6 are used as the enable pins for PWM speed control, while D8-D11 are used for the motor directions.

For the HC-SR04, I used D2 for TRIG and D3 for ECHO.

Once the circuit looked right, I used it as the reference for the real wiring.

<img width="1893" height="1016" alt="screenshot-2026-08-23_17-04-26" src="https://github.com/user-attachments/assets/c663742c-41a8-4e80-9196-d9a8582f6517" />


**Total time spent: 2 hours**

# August 20: Code

I wrote the Arduino code around the circuit.

The rover reads commands through serial at 9600 baud. `F`, `B`, `L`, `R` and `S` control the movement. I also added `+` and `-` for changing the speed and `D` for requesting the distance.

The starting speed is 180 and it can be changed between 0 and 255.

After the basic movement was working, I added the HC-SR04. The forward command checks the distance before moving. If something is within 20 cm, the rover stops instead of moving forward.

I also added a timeout to the ultrasonic reading so that a missing echo doesn't cause the rover to wait forever.

<img width="1380" height="902" alt="image" src="https://github.com/user-attachments/assets/20db4d12-8654-4cf2-88d3-4565070b155c" />

**Total time spent: 3 hours**

# August 20: Real Thing

After finishing the online circuit and code, I built the actual rover.

I connected the Arduino, L298N, four motors and HC-SR04 according to the circuit and then tested the commands one by one. I checked the motor directions first and then tested the ultrasonic stop.

Once the basic movement and obstacle detection were working together, I recorded the demo and added the project files to the repository.

The final prototype is controlled from the phone through USB serial, while the Arduino handles the motors, speed control and ultrasonic distance check.

<img width="3840" height="2160" alt="IMG_20260823_223311_281" src="https://github.com/user-attachments/assets/81f6659d-6e55-4b87-aa86-1a70217f3ec6" />

/demo.mp4

**Total time spent: 3.5 hours**
