# Posture Monitoring System
<img width="5617" height="2415" alt="Second prototype" src="https://github.com/user-attachments/assets/77af4ad8-f7e4-42b2-a6ee-84c5152b8b21" />

An Arduino posture monitoring system that uses **two MPU-6050 accelerometer sensors** to measure the orientation of the upper and lower back and provide real-time posture feedback through a **16×2 LCD display**.

## Project Overview

This project was designed to monitor sitting posture by measuring the angle of different parts of the back(upper and lower). During startup, the user sits in their desired posture while the system performs a short 5s calibration.

The system then continuously measures the user's current angles and calculates how far they have deviated from the initiated position.

## How It Works

1. The Arduino initializes the two MPU-6050 sensors and the LCD display.
2. The user sits in their desired posture during a **5-second calibration**.
3. The system records the upper- and lower-back angles as baseline values.
4. The accelerometers continuously measure the current orientation.
5. The Arduino calculates the **pitch angle** using the X, Y, and Z acceleration values.
6. The current angle is compared with the calibration baseline.
7. The angular deviation is classified as:
   * **Good**
   * **Medium**
   * **Bad**
8. The results are displayed on the LCD and sent to the Serial Monitor.

## Components

* Arduino Uno
* 2 × MPU-6050
* 16×2 LCD Display
* Jumper wires
* Breadboard
* Uploading Cable

## Communication

The two MPU-6050 sensors communicate with the Arduino using **I²C**.

Because both sensors are the same device, they use different I²C addresses:

| Sensor      | Location   | I²C Address |
| ----------- | ---------- | ----------- |
| MPU-6050 #1 | Upper Back | `0x68`      |
| MPU-6050 #2 | Lower Back | `0x69`      |

The LCD uses a parallel interface connected to Arduino digital pins.

## Angle Calculation

The project currently uses the **accelerometer** of the MPU-6050. The gyroscope is not included.

The raw acceleration measurements are converted into acceleration in terms of `g` and then used to calculate the pitch angle(y-axis):

```text
Pitch = atan2(-X, √(Y² + Z²)) × 180 / π
```

The calculated angle is compared with the angle recorded during calibration.

```text
Deviation = |Current Angle − Reference Angle|
```

## Posture Classification

The system uses different thresholds for the upper and lower back.

### Upper Back

| Deviation | Status |
| --------: | ------ |
|     < 20° | Good   |
| 20°–29.9° | Medium |
|     ≥ 30° | Bad    |

### Lower Back

| Deviation | Status |
| --------: | ------ |
|     < 10° | Good   |
| 10°–14.9° | Medium |
|     ≥ 15° | Bad    |

These thresholds are configurable in the Arduino code.

## Example LCD Output

```text
U:12.5°   Good
L:6.2°    Good
```

If the user's posture deviates further:

```text
U:24.7°   Medium
L:12.1°   Medium
```

## Serial Monitor

The Arduino also outputs the raw calculated angles and deviations for debugging and analysis.

Example:

```text
Upper_Raw: -12.40 | Upper_Dev: 18.20 || Lower_Raw: 5.30 | Lower_Dev: 7.10
```

## Future Improvements

Possible future improvements include:
* Make it more economically fit the sitting body posture
* Make it wireless by using bluetooth
* Creating a historical dashboard for analysis
* Add vibration or buzzer for posture alerts

## Project Structure

```text
Posture-Monitoring/
│
├── Journal.md
├── MPU_BodyPosture.ino
└── README.mdJournal.md
```
# Innovator Journal — Posture Monitoring System
## 1. Starting Point

During this unit, I became most interested in MPU as it complexity is similarly to matrix as their 3 axis where I learning the basic at this time, which linked my interest into MPU. As I also pick LCD display to used it into motoring real time information with limitation on the representation with only 16x2 spaces.

## My first prototype
<img width="4032" height="3024" alt="First Prototype" src="https://github.com/user-attachments/assets/c84cead2-8e0c-4fd2-bac9-119f3cefd640" />

At first, I want to build measurement system that show how how far an object had been lifted and at what angle it had been tilted. My idea is to used MPU to measure the angle and the location it have been lifted. 

## Changing concept to the second prototype
<img width="800" height="514" alt="15-279-WEB" src="https://github.com/user-attachments/assets/832fdc33-6853-4815-97f6-7aabc98fe0a8" />


While researching sensors and thinking about how I could make the project more meaningful and impactful, I realized that the MPU-6050 could be used to measure orientation and tilt. Instead of only measuring an object being lifted, after brainstroming the idea, I came out with "human posture".


## 2. New Component

For this project, I chose the MPU-6050 accelerometer/gyroscope module.

I used two MPU-6050 modules so that I could monitor two different parts of the body: the upper back and lower back.

The sensors communicate with the Arduino using I²C. Since both sensors normally use the same I²C address, I configured one sensor as 0x68 and the other as 0x69 using the AD0 pin.

## 3. My Goal

My goal was to create a system that could measure the orientation of two parts of the back:
* Upper back
* Lower back

Then set a range for medium, and bad posture.

## 4. What I Tried
I tried adding an buzzer to this project to improve the alarm system when it reach medium and bad posture. However, when I tried testing it, it keep beeping continuously instead of only activating after medium (slower) and bad(faster) posture.

## 5. What I struggled
Eventhough the code is working, I wonder why is work as I deeply learning from everyline and it meaning. Until almost the end there a function that is not fimilar to my mind, but I guessed that it was related to calculating the angle. This was one of the most challenging parts of the project because it required me to understand not only Arduino code, but also some mathematics and how accelerometer data represents physical orientation.

## 6. Peer Support
I helped Sean to connect LCD display, where I show him step by step of checking where is the problem and why is it not working. Additionally, this weekend I also helped him fix his broken LCD display, but this problem is weird as the light is on but the letter showed. I checked the wiring for LCD display but there's nothing wrong, so I shifted to what component he have that might interupted LCD. Which he used motor where the wiring is fine, so I checked the code where he seem didn't include motor into the code yet, that might be the reason why it is not working. This show me that the problem might not come from itself rather than something that work together and might end up be the problem itself.

## 7. Reflection

What kind of problem or situation could this input or output be useful for, and for whom?
What would need to change or be added to your current build to actually be useful in that situation?
What's one skill from this unit (wiring, debugging, reading a datasheet, debouncing, etc.) that you'd rely on most if you kept developing this idea?

## Resources
https://www.youtube.com/watch?v=7VW_XVbtu9k

http://nxp.com/docs/en/application-note/AN3461.pdf
