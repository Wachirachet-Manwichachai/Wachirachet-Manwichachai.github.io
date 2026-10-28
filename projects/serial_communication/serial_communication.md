# Serial Communication between Arduino and HTML Project
# Day 1: Hardware Setup
<img img style="max-width: 100%; height: auto; display: block;" alt="Screenshot 2026-10-16 122404" src="https://github.com/user-attachments/assets/4244a4f0-fb9e-4dea-92f6-cdd5e8ecb3d4" />

On the first day, we focused on connecting the joystick to the Arduino and understanding how the hardware works. We used online diagrams and tutorials to identify the correct connections and learn how the joystick sends input signals to the Arduino. Additionally, we also put led for round indicator, which the blue led represent the player and the other 2 red led represent the opponent. Lastly, the button perform as play round(selected card or skip) which can be very interactive combined with joystick and LEDs. After connecting the components, we checked the wiring to make sure everything was ready for software testing. We also code it to print the output for further software development.

# Day 2: Software Testing and Debugging
<img img style="max-width: 100%; height: auto; display: block;" alt="Screenshot 2026-10-16 122404" src="https://github.com/user-attachments/assets/064b2649-105d-468a-b70e-8634259dce13" />

On the second day, we focused on programming the Arduino to respond to joystick movements. We tested the code, observed the outputs, and debugged problems. The biggest challenge is to understand the joystick to HTML transition which mainly focuses on fucntion. When the player moves the joystick, the Arduino sends commands such as NAV_LEFT or NAV_RIGHT to JavaScript, which moves the highlighted card on the screen. Pressing the joy stick send out selecting command to Java, allowing the player to select or deselect cards. JavaScript can also send commands back to the Arduino to control the turn indicator LEDs. This allows the physical hardware and the webpage to work together as one interactive system. 

# Showcase

https://github.com/user-attachments/assets/f28ac6df-73eb-40e9-8fec-da830dfb357b

This video how to execute the connection and show what does our software capable of connecting with the Landlord game.

# AI and Online Resources
AI helped us write, understand, and debug code. Google and YouTube tutorials were also useful for learning about the circuit connections and how the joystick interacts with the Arduino then transfer it to HTML which building the foundation of curcuit and coding skill before applying it alongside with ai. These resources helped us troubleshoot problems and make progress more efficiently.

# Source

This video show how to communicate between potentiometer to HTML but we get the basic ideas and adapt it to our projects.
https://www.youtube.com/watch?v=gQYsUjT-IBo
