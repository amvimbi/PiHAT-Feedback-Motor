# PiHAT-Feedback-Motor
The  microHAT  is  designed  to  interface  with  and  drive  a  motor  with  an  accurate  positional feedback loop-circuit. 
It will be mounted on a Pi Zero which will provide the compute capacity to achieve the desired specifications. 
This configuration is ideal for electromechanical systems where  high  spatial  precision  is  needed.  By  interfacing 
it  with  the  Pi  parent  board,  a  vast assortment  of  functionalities  can  be  realized.  These  include  the  logging
and  storing  of performance metrics -in real-time-on a micro-SD, scaling up and or integration into a larger system through
the micro-USB port. The General-Purpose Input Output (GPIO) pins will be configured in analogue, input or output mode to 
enable the sensorsand feedback modules to interact with the Pi which will -in response-initiate desired actions such as 
altering the torque and turning on indicator LEDs. All in all, with its high clock speed, the Pi Zero will allow for high 
response, low positional feedback latency operation. Use cases of the circuit include but are not limited to driving a high 
precision robotic arm used in surgery, an electronic steering system vehicle which require low latency and good feedback and
control for wind turbines to ensure that they get the highest wind incidence as this requires accurate position awareness.

Possible use cases
Control robotic armfor cancer operations-to remove all the tumour and surrounding cancer tissue effectively
Can drive Robots used for handling radioactive & bio-hazardous experiments

The feedback circuitry will function as follows:

The position feedback circuit is connected through a buffer to GPIO 17 which is configured to analogue mode. The position feedback circuit will comprise a circular resistive track on which a wiper slides, such that the wiper voltage changes linearly with angular displacement. This pin will have a voltage whose amplitude corresponds to the angular displacement of the motor which makes this spatial data to be known by the controller at any instant. Parallel to this pin, a differentiator is connected which gives out a voltage corresponding to the rate of change of the displacement (velocity). The output to the latter circuit is connected to 27 of the HAT which is configured to analogue mode, the microcontroller is programmed to monitor the amplitude of  this  voltage  and  whether  it  is  changing  and  respond  in apredetermined  manner.  If  this amplitude is too low, then the motor is spinning too slowly and the output GPIO pin 23 which operated in output mode in the microcontroller goes high and increases the field current which torques  the  motor  to  a  higher  angularvelocity.  By  monitoring  the  rate  of  change  in  the amplitude, the Pi also keeps track of angular acceleration.
