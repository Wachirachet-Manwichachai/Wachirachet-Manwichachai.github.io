# Step 1 CAD + Material
The first step involve in indentifiying material crucial for the 3D scanner project. For scaanning part we need ir sensor to measure accurately, but also need the ability to trace the object which the stepper motor come in play. Lastly in order to use stepper motor we need to use stepper driver for limiting and controlling the power as motor can't handle the direct power.

Material: 1 Sharp 2Y0A21, 2 Stepper motor 17HE15-1504S, 2 Stepper driver, 1 CNC Shield v3, 1 Arduino motherboard, Wires

# Step 2 Hardware Setup
As we gathered all the materials this is the step by step procedure:
#### 1. Put the shield on top of Arduino motherboard
#### 2. Set the limit of stepper driver by using multimeter measuring power(potentiameter on the driver) and ground (on the GND)
#### 3. Connecting the IR sensor to CNC Shield. Pin 1 is OUT/Signal connecting to coolen(right side), pin 2 is GND connecting to GND(right side), and lastly pin 3 is VCC/Vin connect to 5v right accross GND
#### 4. Our prepared Stepper motors connecting to 4 pins on the right side of the motor driver, the configuration of the wire you can follow to the youtube link down below.
#### Tip: Connecting EN(enable) with GND (On the left side) so it force the stepper motor drivers to stay permanently enabled without needing software control.
#### https://www.youtube.com/watch?v=dR4I1YjNKqA
Here the diagram of the CNC Shield for clarification:
<img style="max-width: 100%; height: auto; display: block;" alt="image" src="https://github.com/user-attachments/assets/924521da-a175-48b8-a3e0-87855efc5b34" />

https://global.sharp/products/device/lineup/data/pdf/datasheet/gp2y0a21yk_e.pdf
# Step 3 Software Setup/Coding
We chose VScode as our code editor as it can be useful for long-term usage as it able to plot in 3D with Matlab extension which far superior to Arduino. In order communicate from computor with the motherboard using VScode we need an extension and we picked PlatformIO IDE. 
#### 1. Download VScode and C++ langauge
#### 2. Download PlatformIO IDE on VScode
#### 3. After creating new project this will be the folder that I had created, the files that we are going to use is platformio.ini and main.ccp in src folder. platformio.ini is a ecosystem/environment embedded into systems which is essentially the setup for the microcontrollers. main.ccp is the central code just like what we are coding in Arduino IDE.
<img style="max-width: 100%; height: auto; display: block;" alt="Screenshot 2026-11-12 202439" src="https://github.com/user-attachments/assets/b4aef7f3-6ca9-4252-8ce4-184d76762cf3" />

# Challenge/Problems
### 1. Stepper motor stalling: 
We had the stepper motor moving but as in the present time it hadn't worked as we tried to figure what's the problems, our main suspicion is an incorrect motor coil connection. Since stepper motors operate using two separate electromagnetic coil pairs, connecting the wires in the wrong sequence can prevent the motor from rotating correctly. 
### 2. Uploading Error: 
Down here is error line occur when we are uploading the code. This line indicate that the controller is failed to sinc as it tried 10 times before exit(line down below). I tried to change uploading cables and usb-c adapter couple times and we're still figuring out what's the problem.
### Sample Example:
Error: programmer is not responding
Warning: attempt 1 of 10: not in sync: resp=0x00

Error: unable to open port /dev/cu.usbmodem101 for programmer arduino
Failed uploading: uploading error: exit status 1
# Our Next step
### Fixing 

# Our future plan
### Controling 
