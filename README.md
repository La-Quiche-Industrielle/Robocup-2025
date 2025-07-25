# Robocup-2025


## What is Robocup?
[Robocup Junior Soccer Open](https://junior.robocup.org/soccer/) is a league of the international robotic competition: [RoboCup](https://robocup.org).
For this competition, we need to create _two fully autonomous robots_ that play _soccer_ against other teams. We have to design, build and program the robots without external help. This is a really challenging problem because the robots need to be fully autonomous. They need to detect the ball and try to go towards it to hopefully push it towards the goal. A camera system is needed to try to detect the ball based on its color (it's an orange golf ball) and to detect the opponent's goal.

[Learn more about the competition](https://robocup-junior.github.io/soccer-rules/master/rules.html)

## The robots
![Our Robot](../media/spinning.gif)

The robots were built with individual components we found online, that we meshed together using communication protocols such as uart. The frames were 3d printed, and the cone was manufactured with CNC machining.

[More on the components we used](./components.md)

While we prepared for the competition, the robots could reliably place goals and were rather fast:
![A robot placing a goal](../media/goal.gif)

### What failed
The robots broke in many ways during the national competition which meant we couldn't play for many of the matches:
- The wheels got disconnected from the motor's axies many times, which meant the whole robot became unable to play.
- Many of our N20 motors broke, which meant we didn't even have enough motors for both robots at the end of the competition
- An esp32 broke during the competition, and one of our replacement microcontrollers also failed when we opened the package.
- One of the batteries had a short circuit. Thankfully, the BMS (battery management system) protected the batteries from the short circuit. 

### How we'll fix these issues
- We created a simple 3d printed junction between the motors' axies and the wheels. This worked very well initially, but we hadn't taken the plastic's wear into account nearly enough. For next year, we'll only use metal components on important structural parts such as this.
- Last year, we chose N20 motors because of their low cost and good reviews. During the competitions, we often went above their torque limit, thus hurting the gears and breaking the motors. The N20 motors' torque is around 1kg.cm, and we realised that this wasn't nearly enough for what we wanted our robots to do. Next year, we'll invest in some better motors given sufficient funding, and hard code the torque limit into the program to slow the robots down before they could reach the torque limit and hurt the components.
- We bought many of our components on Aliexpress to reduce costs. Esp32s from aliexpress were within our price range, so we used these microcontrollers. For next year, we'll probably use better and faster microcontrollers such as a [teensy](https://www.sparkfun.com/development-boards/microcontrollers/teensy.html) and from better suppliers if we have the budget to do so.
- The battery had a short circuit because the wiring had become very difficult to work with. We had several dozens of wires going through the robot, and a positive and negative wire must have touched causing the short. This year, we tried designing a pcb, but it had a short circuit. Next year, we'll design a better pcb for the whole robot and try to find more data on pcb design before sending the design to a manufacturer.

### What we learned from our mistakes

___We can't expect that the robot won't break:___
This year was a rather frustrating experience as we had worked very hard to create fast and functional robots only to see them fail miserably the day of the competition. We managed to have the robots place goals and avoid going out of bounds, and search for the ball if it couldn't see it and many other challenging actions only to see most components on the robots fail. We had spent hours programming the robots and making them move around on the field, and yet the numerous issues only arised the day of the competition. What we have learned from this is that we need to stress test our robots a lot more. We can no longer expect something to work only because it has worked in the past. Next year, we will push the robots to their limits. We will make them move until something breaks then rebuild that part with a lot more redundancy. We will also source better components given te ressources, and try to build redundancy into each and every part of the robot. We have learned that ___we can't expect that the robot won't break.___, but we need redundant systems to make sure that the system continues to work even if the primary system fails.

## Our Website
Find out more about the team at laquicheindustrielle.com.
