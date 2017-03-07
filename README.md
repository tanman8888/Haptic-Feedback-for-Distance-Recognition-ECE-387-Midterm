# Haptic-Feedback-for-Distance-Recognition-ECE-387-Midterm
I've integrated an HC-SR04  ultrasonic sensor with Sparkfun DRV2605L haptic driver.

READ ME

The objective of this project was to provide some type of feedback for distance recognition.
I needed a sensation that doesn't distract the user from operating the machine.The perfect
solution for this is haptic feedback. There are many different ways to incorporate haptics
in a project, but I ended up using the SparkFun DRV2605L Haptic Motor Driver. There are
several other options to drive a vibration motor, but this chip makes things quite a bit
easier. The chip has built in waveforms that you can access and it also has a smart loop
architecture that helps detect and fix problems with the motor. The chip is compatable
with both erm and lra motors. I chose to use a linear resonant actuator (lra) because 
of how compact they are. They are essentially just a mass on a spring and as a current
is flowing through the spring, the mass will move up and down, wich creates a vibrating
sensation. I have marked in the code what you'll need to change if you decide to use an
erm. The haptic driver has 8 different modes that it can run on:
 1) 0x00: get out of standby and use internal trigger (using GO command)
 2) 0x01: get out of standby + use External Trigger (edge triggered)
 3) 0x02: get out of standby + External Trigger (level triggered)
 4) 0x03: get out of standby + PWM input and analog output
 5) 0x04: use Audio to Vibe
 6) 0x05: use real time playback
 7) 0x06: perform a diagnostic - result stored in diagnostic bit in register 0x00
 8) 0x07: run auto calibration.
I worked with the real time playback in order to provide a reliable system for
detecting distance. Ive included notes in the code to help incorporate the other
modes. There is also a breakdown of each function that is available for the
driver for arduino. It's nice to see what each function is actually doing.
Working with the HC-SR04 ultrasonic sensor was very straight forward with the arduino library.
The example code provided in the arduino IDE provided the exact data that I was needing.
There are weird things that happen if there is an object too close to the sensor.
The data points lower than 3 cm tend to jump to very negative values or they jump to
random value. It also has trouble detecting objects that arn't flat. In order to get
around this, I created a system to throw out values that we shouldn't expect to see 
in the real world. The calculated data is then used to indicate if there should be 
feedback or not. It also determines the type of feedback that is provided.

Possible applications:
1) I intend on incorperating this sytem into a larger project that I'm working on. I want to add
   this to an RC car to provide feedback if it gets too close to something.
2) Long term, I'd like to see this incorporated into cars. I'd like the vibration motor to provide
   feedback that isn't as distracting as noise, that will also be significant enough to get the
   user's attention. The motor will be placed in the steering wheel and the ultrasonic sensor 
   will be set up like how the current detecting systems are.
 
