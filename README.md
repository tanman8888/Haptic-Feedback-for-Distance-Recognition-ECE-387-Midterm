# Haptic-Feedback-for-Distance-Recognition-ECE-387-Midterm
I've integrated an HC-SR04  ultrasonic sensor with Sparkfun DRV2605L haptic driver.

READ ME

The objective of this project was to provide some type of feedback for distance recognition.
I needed a sensation that wouldn't distract the user from operating the machine.The perfect
solution for this is haptic feedback. This project consists of anultrasonic sensor integrated
with a haptic driver. The wiring is very simple and I've tried to make the code easy to 
understand so that you can use it for your projects!

There are many different ways to incorporate haptics in a project, but I ended up using the 
SparkFun DRV2605L Haptic Motor Driver. There are several other options to drive a vibration
motor, but this chip makes things much easier. The chip has 134 built in waveforms that you 
can access and it also has a smart loop architecture that helps detect and fix problems with
the motor. The chip is compatable with both erm and lra motors. The haptic driver also has 8
different modes that it can run on I chose to use a linear resonant actuator (lra) because of
how compact they are. They are essentially just a mass on a spring and as a current is flowing
through the spring, the mass will move up and down, which creates a vibrating sensation. I
have marked in the code what you'll need to change if you decide to use an erm. I worked with
acouple modes to demonstrate the different features that the driver has to offer. There is 
also a breakdown of each function that is available for the driver for arduino in the example
code file. It's nice to see what each function is actually doing. 

Working with the HC-SR04 ultrasonic sensor was very straight forward with the included arduino
library. I break it down more in depth in the wiki. The example code provided in the arduino 
IDE provided the exact data that I was needing. There are weird things that happen if there are
objects too close to the sensor. The data points lower than 3 cm tend to jump to very negative 
values or to random value altogether. It also has trouble detecting objects that arn't flat.
In order to get around this, I found a combination of the bode rate and the braking time that 
seems to avoid problems of false detection.The analog data is converted to digital and then 
used to indicate if there should be feedback or not.I will explain this in more detail in the 
wiki. It also determines the type of feedback that is provided.

Possible applications:

1) I intend on incorperating this sytem into a larger project that I'm working on. I want to add
   this to an RC car to provide feedback if it gets too close to something.

2) Long term, I'd like to see this incorporated into cars. I'd like the vibration motor to provide
   feedback that isn't as distracting as noise, that will also be significant enough to get the
   user's attention. The motor will be placed in the steering wheel and the ultrasonic sensor 
   will be set up like how the current detecting systems are.
 
