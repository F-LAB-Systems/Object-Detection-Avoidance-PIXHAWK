# Object-Detection-Avoidance-HC-SR04--ARDUINO-
This will set you up on how to integrate cheap HC-SR04 ultrasonic sensor and arduino uno for Object detection and avoidance on a Pixhawk 2.4.8 and even the cube(Wiring for the telemetry will start from right i.e 5v will be be on right followed by TX &amp; Rx). The arduino will communicate with the pixhawk and will override the Tx input to achieve avoidance when the sensor detects obstacle. 
Currently the code supports only the PITCH movement(FRONT - BACK) and can be added with ROLL (LEFT - RIGHT) movement aswell.


# NOTE
Please download the Mavlink library provided in my repository and change the path to the mavlink.h as per your systems path to Arduino's library
