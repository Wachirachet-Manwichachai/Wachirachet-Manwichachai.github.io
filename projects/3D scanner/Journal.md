# Step 1 CAD + Material
The first step involve in indentifiying material crucial for the 3D scanner project. For scaanning part we need infared sensor, but also need the ability to trace the object which the stepper motor come in play. Lastly in order to use stepper motor we need to use stepper driver for limiting and controlling the power as motor can't handle the direct power.

Material: 1 Sharp 2Y0A21 F 56 B, 2 Stepper motor 17HE15-1504S, 2 Stepper driver, 1 CNC Shield v3, 1 Arduino motherboard, Wires

# Step 2 Setup
As we gathered all the materials this is the step by step procedure:
### 1. Put the shield on top of Arduino motherboard
### 2. Set the limit of stepper driver by using multimeter measuring power(potentiameter on the driver) and ground (on the GND)
### 3. Connecting the sensor to external pin on the CNC Shield

<img style="max-width: 100%; height: auto; display: block;" alt="image" src="https://github.com/user-attachments/assets/924521da-a175-48b8-a3e0-87855efc5b34" />

https://global.sharp/products/device/lineup/data/pdf/datasheet/gp2y0a21yk_e.pdf
# Step 3 Coding
