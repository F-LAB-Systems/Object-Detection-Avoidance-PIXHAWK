# Object-Detection-Avoidance using HC-SR04 and ARDUINO on Pixhawk
This will set you up on how to integrate cheap HC-SR04 ultrasonic sensor and arduino uno for Object detection and avoidance on a Pixhawk 2.4.8 and even the cube(Wiring for the telemetry will start from right i.e 5v will be be on right followed by TX &amp; Rx). The arduino will communicate with the pixhawk and will override the Tx input to achieve avoidance when the sensor detects obstacle. 
Currently the code supports only the PITCH movement(FRONT - BACK) and can be added with ROLL (LEFT - RIGHT) movement aswell.


# NOTE
Please download the Mavlink library provided in my repository and change the path to the mavlink.h as per your systems path to Arduino's library



PITCH CALCULATION

----EXAMPLE 1----

Assume...

Distance from Obstacle (FRONT_SENSOR) = 40cm } Drone must move back to avoid the obstacle

EQUATION ...

PITCH_BACK = 1500+30+((70-FRONT_SENSOR)*6);
PITCH_BACK = 1500+30+((70-40)*6);
PITCH_BACK = 1500+30+((30)*6);
PITCH_BACK = 1500+30+(180);
PITCH_BACK = 1500+210;
PITCH_BACK = 1710; // This is the Pitch value that must be sent to the pixhawk when an object is detected at 40cm



----EXAMPLE 2----

Assume...

Distance from Obstacle (BACK_SENSOR) = 60cm } Drone must move back to avoid the obstacle

EQUATION ...

PITCH_BACK = 1500+30+((70-FRONT_SENSOR)*6);
PITCH_BACK = 1500+30+((70-60)*6);
PITCH_BACK = 1500+30+((10)*6);
PITCH_BACK = 1500+30+(60);
PITCH_BACK = 1500+90;
PITCH_BACK = 1590; // This is the Pitch value that must be sent to the pixhawk when an object is detected at 40cm
