# L298N Motor Driver
<img src = "l298n.jpg" width="500">

## What is the L298N?
The L298N is a motor driver chip. What this means is that we connect the L298N in between the Arduino and the motors we're using. By having this chip as a middleman, we're able to accomplish more complex functionality more easily, and we can maintain safety better. The motor driver chip allows us to control the spinning direction of motors using an H-Brige (as demonstrated below). It also makes it more clear how to wire the motors together. In addition it regulates the power given to the motors to lessen the chances of frying any component.  

##### Useful graphic for understanding how an H-Bridge works: 
![H-Bridge Gif](https://lastminuteengineers.com/wp-content/uploads/arduino/H-Bridge-Working-Motor-Direction-Control-Animation.gif)

### Sample Code
An example code that can be used to test out the motors can be found in the current directory entitled: motorTest.ino  
This code tests the motor functionality running forwards and backwards. It also tests out the speed control of the motors.  
The pins in the program match the pins in the wiring diagrams shown below.

### Powering the Motor Driver:
When powering 4 motors for tank drive, the two motors on the left should be in parallel with each other, and the two motors on the right should be in parallel with each other.  
In this configuration the motor driver typically needs to be supplied with ~9V. However, very often a 9V battery won't supply enough current for the motors to run. In addition, sometimes 4 AA batteries in series can power the motors, however once they drop just a little bit in voltage, they will no longer work.  
There are two ways to power it that should work consistently. If the student has a battery pack that can sit 6 AA batteries (or 2 battery packs that can be used in series), this will supply enough voltage and current to power the motors for a decent amount of time. If the student can't wire 6 AA batteries in series, then they can power Arduino using the wall adapter and then wire the V_in pin from Arduino into the +12V on the L298N.  
If the ESP32 must be used for the project, then this latter method can still work by using the Arduino as a power source for both the ESP32 and the L298N. In this case, connect the wall adapter to the Arduino, connect V_in from Arduino to the L298N's +12V pin. Then connect 3.3V and GND on the Arduino to 3V3 and GND on the ESP32 respectively.
Below are illustrations of these 2 methods of connecting: 
## Diagrams for Powering the Motor Driver
### Battery Power
![Battery Power](L298N_BatteryPower.png)
---
### Wall Power
![Wall Power](L298N_WallPower.png)
### Common issues:
Often the students won't realize that they must take the caps off of the EN_A and EN_B pins in order to allow them to control the speeds of the motor drivers. Some students also try to connect the wires to EN_A and EN_B with the caps still on top too.  
If one or more motors motors is rotating slower than the others or are not rotating at all, this is likely due to power issues. So refer to the guide above for powering. If the motors were working and then stopped working without a change in the wiring this is also likely due to power issues.  

Wires typically don't stay attached to the motors very well. Therefore soldering is recommended in order to keep wires secured to the motors. For testing purposes, jumper wires can usually be wedged into the fins on the motor. Alternatively jumper cables can be used for a more secure connection.
