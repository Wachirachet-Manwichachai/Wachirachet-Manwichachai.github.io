# Stepper motor
# Day 1
As we look into the tutorial stepper motor video, I just know that the stepper motor needed a motor driver to prevent the motor coils from overheating and burning out when using a high-voltage power. However, the motor driver is not automatically limit our wanted power. So, we manually limit the output adjusting the motor drive's potentiometer and monitoring the DC(Direct current) voltage with a multimeter until it reached the target value.

https://github.com/user-attachments/assets/a8a8ddc4-52a2-4b73-b4a1-382a5c9d115d

Challenge:
When we are trying to set the limit multiple time but the DC voltage is at 0.00v. That make me confussed as I plug my arduino uno, but then I thought about stepper motor and motor driver diagram, which include an independant power supply which make me think that it might be why our measurement isn't working. When we plugin the power supply, we can able to see and set the limit voltage.

<img width="3024" height="4032" alt="IMG_1870" src="https://github.com/user-attachments/assets/e1740c2c-b510-4114-903f-819e1e5d0849" />

This was the point where we finished the wiring of the driver. It took a long time since it was a new thing for all of us. We used the youtube video to help us better understand the wiring and how it functions, and in this picture we finished the wiring with the help of the youtube video and it was a major checkpoint for us. 

# Day 2
As we able to set the limited power input we explore more into programming and how to control the stepper motor. The first exploration is the code from the tutorial video itself(1st code), which focus mainly on the speed not the direction as the code only provide one directional movement with difference speed by setting the value into a function(Delay for HIGH(5v or 3.3v), and LOW(0v)).

## AI Usage
In this project, we used a lot of AI. AI helped us write the code and we also used AI to understand it's code that was given to us. Sometimes it would give out some bugs, and we would use AI to help us debug it and help us understand the circuit. Google also played a big part for the wiring. For example, we didn't really understand how the driver motor worked so we went onto google and looked at a circuit diagram explaining the wiring process and how the device is used. A youtube video also helped us significantly. Another great source to learn is youtube, as it contain lot of tutotial, information, and explanation in order to understand the topic. As for this project we started from tutorial for how to use the stepper motor and how to use the multimotor which helps us detect the Amps for the driver motor. Overall, the usage of internet was extremely helpful as it helped us develop code, help us understand both the electronics and circuit and saved us alot of time. 

[Watch the Tutorial Video](https://www.youtube.com/watch?v=wcLeXXATCR4&t=687s)
