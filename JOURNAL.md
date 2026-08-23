---
title: "ROVE"
github: "YOUR_GITHUB_USERNAME/ROVE"
description: "Building ROVE, a phone-controlled rover."
created_at: "2026-08-23"
---

# August 23rd: Planning ROVE

Today I started working on ROVE.

I spent the first part of the session figuring out what I wanted the first version to actually do. Instead of trying to build the complete idea immediately, I decided to start with a simple phone-controlled rover with obstacle avoidance.

I worked out the basic circuit and decided how the Arduino, L298N, motors and HC-SR04 would connect.

I also spent some time tinkering with the components and figuring out how everything would fit together.

![Circuit planning](wiring-diagram.png)

**Time: 12 PM – 1 PM**

---

# August 23rd: Writing the Code

After finishing the initial planning, I started writing the Arduino code.

I added the basic movement commands for forward, backward, left, right and stop. I also added PWM speed control and code for reading the HC-SR04.

The main thing I wanted was for the rover to stop if it detected something too close while moving forward.

**Time: 2 PM – 4 PM**

---

# August 23rd: Building ROVE

I moved on to the physical build.

I assembled the chassis, mounted the motors and connected the L298N motor driver to the Arduino.

I then wired up the HC-SR04 and connected the rest of the components according to the circuit I had planned earlier.

A lot of this session was just testing connections, moving things around and making sure the physical build matched the circuit.

![ROVE build](rover-build.jpg)

After around six hours of building and tinkering, I had the first physical version of ROVE put together.

**Time: 4 PM – 10 PM**

---

# August 23rd: First Prototype Complete

The first prototype is now assembled.

I now have the basic hardware needed for ROVE to move and detect obstacles. The next step is to build the phone controller and connect it to the Arduino so I can actually drive ROVE from my phone.

**Total time spent today: 8h**
