# 🚨 Touch Activated Alarm

A hardware implementation of a **Bistable Multivibrator** using the NE555 timer. This project demonstrates how to create a simple 1-bit memory cell that toggles between two stable states using manual inputs.

---

## 💡 Overview

This circuit acts as a basic memory latch (SR Latch). Once triggered, it "remembers" its state and keeps the alarm active until a manual reset is performed. It is a perfect bridge between pure analog electronics and digital logic.

### How it works:
* **Logic:** The circuit uses a Set/Reset (SR) configuration. Pressing the **"Set"** button pulls the Trigger pin (Pin 2) LOW, latching the output to HIGH. The **"Reset"** button pulls the Reset pin (Pin 4) LOW, forcing the output back to its initial LOW state.
* **Driving Loads:** Since the 555 output drives both a LED and a Buzzer, a **BC547 NPN Transistor** is used as a switch. This demonstrates current amplification and how to safely drive multiple output devices.
* **Key Concepts:** * Pull-up resistor configuration.
    * Transistor switching and saturation.
    * Basic debouncing principles.
    * Detailed IC pin functions (VCC, GND, TRIG, RESET, OUT).

---

## 🛠️ Bill of Materials (BOM)

| Quantity | Component | Description |
| :--- | :--- | :--- |
| 1 | **NE555 Timer IC** | The brain of the latch |
| 1 | **BC547 Transistor** | NPN BJT for switching the load |
| 1 | **Active Buzzer** | Audible alarm |
| 1 | **Red LED** | Visual indicator |
| 2 | **10kΩ Resistors** | Pull-up resistors for Set/Reset buttons |
| 2 | **1kΩ Resistors** | Current limiting for LED and Transistor base |
| 1 | **10nF Capacitor** | Noise filtering for the Control pin |
| 2 | **Push Buttons** | Tactile switches for Set and Reset |

---

## 📂 Project Media

* **Schematic:** [See `schematic.png`](./schematic.png) for the full circuit diagram.
* **Crumb Demo:** [View `demo.mp4`](./demo.mp4) to see the 3D breadboard simulation in action.

---

## 🎓 Lessons Learned

* **Floating Pins:** I discovered why the 555 timer requires pull-up resistors on the Trigger and Reset pins—without them, static electricity or noise could cause "ghost" triggering of the alarm.
* **Transistor Logic:** Realized the importance of the base resistor (R4) to prevent damaging the transistor while ensuring it fully enters the saturation region to act as a closed switch.
