# Step 1 CAD + Material
The first step involve in indentifiying material crucial for the 3D scanner project. For scaanning part we need ir sensor to measure accurately, but also need the ability to trace the object which the stepper motor come in play. Lastly in order to use stepper motor we need to use stepper driver for limiting and controlling the power as motor can't handle the direct power.

Material: 1 Sharp 2Y0A21, 2 Stepper motor 17HE15-1504S, 2 Stepper driver, 1 CNC Shield v3, 1 Arduino motherboard, Wires

# Step 2 Hardware Setup
As we gathered all the materials this is the step by step procedure:
#### 1. Put the shield on top of Arduino motherboard
#### 2. Set the limit of stepper driver by using multimeter measuring power(potentiameter on the driver) and ground (on the GND)
#### 3. Connecting the IR sensor to CNC Shield. Pin 1 is OUT/Signal connecting to coolen(right side), pin 2 is GND connecting to GND(right side), and lastly pin 3 is VCC/Vin connect to 5v right accross GND
#### 4. Our prepared Stepper motors connecting to 4 pins on the right side of the motor driver, the configuration of the wire you can follow to the youtube link down below.
#### Tip: Connecting EN(enable) with GND so it force the stepper motor drivers to stay permanently enabled without needing software control.
#### https://www.youtube.com/watch?v=dR4I1YjNKqA
Here the diagram of the CNC Shield for clarification:
<img style="max-width: 100%; height: auto; display: block;" alt="image" src="https://github.com/user-attachments/assets/924521da-a175-48b8-a3e0-87855efc5b34" />

https://global.sharp/products/device/lineup/data/pdf/datasheet/gp2y0a21yk_e.pdf
# Step 3 Software Setup/Coding
