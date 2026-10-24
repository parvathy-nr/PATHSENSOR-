# 🚧 **PathSensor: Ultrasonic Proximity Alarm**


> 🔊 PathSensor turns a budget Arduino and an ultrasonic sensor into an early-warning system: step within 50 cm of an obstacle and it sounds off instantly, with no internet, no apps, no fuss.

---

## 📖 **Overview**

PathSensor is a low-cost obstacle alert built with an Arduino, an HC-SR04 ultrasonic sensor and a buzzer. It continuously measures the distance to whatever is in front of it and sounds an alarm when something comes within 50 cm.

**❗ Problem it solves:** Obstacles in a walking path or workspace are easy to miss, especially when visibility is poor or attention is elsewhere. PathSensor gives an immediate audible warning using inexpensive, widely available parts.

---

## 💡 **Idea and How It Works**

1. The Arduino sends a 10 µs trigger pulse to the HC-SR04.
2. The sensor emits an ultrasonic burst and holds the echo pin HIGH until the reflection returns.
3. The Arduino measures that pulse with `pulseIn()` and converts it to distance: `distance (cm) = (duration × 0.0343) / 2`
4. If the distance is at or below the threshold (default 50 cm), the buzzer turns on. Otherwise it stays off.
5. If no echo arrives within the timeout (about 5 m), the reading is treated as "out of range" and the buzzer stays off.
6. Each reading is printed to the Serial Monitor at 9600 baud.

---

## 🛠️ **Tech Stack and Components**

| Item | Details |
|---|---|
| 🧠 Microcontroller | Arduino (Uno or compatible)|
| 📡 Sensor | HC-SR04 ultrasonic distance sensor |
| 🔔 Output | Active buzzer |
| 💻 Language | Arduino C++ |
| 🧰 Tools | Arduino IDE |

## 🔌 **Wiring**

| Component | Arduino Pin |
|---|---|
| HC-SR04 TRIG | D3 |
| HC-SR04 ECHO | D2 |
| Buzzer (+) | D5 |
| HC-SR04 VCC | 5V |
| HC-SR04 GND / Buzzer (-) | GND |

---

## ⚙️ **Configuration**

Edit these constants at the top of `pathsensor/pathsensor.ino`:

- `alarmDistance`: distance in cm at or below which the buzzer sounds (default 50)
- `speedOfSound`: speed of sound in cm/µs (default 0.0343, at about 20 °C)
- `echoTimeout`: how long to wait for an echo, in µs (default 30000)

---

## 🚀 **Getting Started**

1. Wire the components as shown above.
2. Open `pathsensor/pathsensor.ino` in the Arduino IDE.
3. Select your board and port, then upload.
4. Open the Serial Monitor at 9600 baud to see live distance readings.

---

## 🎬 **Demo**

- 🔴 **Live demo video:** [https://drive.google.com/file/d/1wg968wVCWe_v7cqkw_OpEXzZd6r5uQPg/view?usp=drivesdk]
- 📹 **Demo video :** [https://drive.google.com/file/d/1wg968wVCWe_v7cqkw_OpEXzZd6r5uQPg/view?usp=drivesdk]
- 📊 **Presentation:** []

## 🔮 **Possible Improvements**

- 📡 **Better sensors:** Swap the HC-SR04 for a more accurate, longer-range sensor such as LiDAR or a waterproof ultrasonic sensor.
- 🎥 **360° camera sensing:** Add a camera to detect obstacles in every direction, not just in front.
- 🧭 **Obstacle-avoidance commands:** Add a command output, such as "turn left" or "stop", so a robot or user knows how to avoid the obstacle.
- 📏 **Distance readout:** Show the exact distance in meters on a display or by voice.
- 🔁 **Multi-purpose use:** Reuse the same design for robots, parking assist, blind-spot warnings and workplace safety.
- 🎚️ **Smarter alerts:** Vary the beep rate with distance and average several readings to reduce noise.
---

## 👥 **Team**

[ARISE]
