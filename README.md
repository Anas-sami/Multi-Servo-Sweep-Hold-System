# Multi-Servo-Sweep-Hold-System
This Arduino Uno system controls 4 SG90 servos. On boot, they sweep together from 0° to 180° for exactly 2s using non-blocking timing. They then lock at 90°, showing smooth transitions from free motion to positional hold—key for robotics. Designed and built by Anas Sami Al-Harthy.

# 🤖 Multi-Servo Sweep & Hold System

---

### **Project Creator & Sole Owner:**
* **Developer:** Anas Sami Al-Harthy
* **Track:** Electronics & Electrical Power Engineering - Smart Methods
* *Note: This project was designed, wired, and programmed entirely and individually by Anas Sami Al-Harthy.*

---

## 📝 Project Description
The **Multi-Servo Sweep & Hold System** is a precise robotic motion control project built around the **Arduino Uno** microcontroller to orchestrate the synchronous behavior of **four SG90 micro servo motors**. This project effectively simulates complex multi-axis robotic movements, such as those found in robotic limbs or advanced steering mechanisms, which require highly coordinated, time-dependent routines.

The system's operation is split into two distinct, deterministic phases:
1. **Synchronous Sweep Phase:** Upon system initialization (powering up the Arduino via USB), all four servo motors activate concurrently, continuously sweeping back and forth from 0° to 180° and back to 0°. This is handled via a non-blocking timing algorithm utilizing Arduino's native `millis()` function, ensuring rigorous temporal accuracy for exactly 2 seconds without freezing the microcontroller unit (MCU).
2. **Positional Hold Phase:** Immediately following the 2-second threshold, the MCU halts the sweep routine and delivers a unified Pulse Width Modulation (PWM) signal to drive all four motors to their center positional baseline (90°). The servos latch and maintain this position firmly, highlighting the system's transition from free continuous motion to rigid positional stability—a critical safety feature in mechanical automation.

---

## 🛠️ Technical Specifications & Components

Every component has been structurally integrated to maintain pristine signal integrity and electrical stability:

| Component | Qty | Technical Specifications & Role | Operating Voltage |
| :--- | :---: | :--- | :---: |
| **Arduino Uno R3** | 1 | The main MCU processing code execution and generating digital PWM control signals. | `5V DC` (via USB or external jack) |
| **SG90 Servo Motor** | 4 | Core micro-actuators delivering a stall torque of 1.8 kg/cm at a 50Hz refresh rate. | `4.8V - 6V DC` |
| **Breadboard** | 1 | Central distribution hub for consolidating and parallelizing power rails (VCC/GND). | - |
| **Jumper Wires** | - | Male-to-Male flexible interconnects for stable signal and power mapping. | - |

### ⚡ Critical Electrical Notes:
* **Current Draw Dynamics:** Under active load, four simultaneous servo motors can draw transient peak currents that exceed the output current capabilities of the Arduino's onboard linear voltage regulator. While direct 5V rail power from the Arduino is perfectly safe within simulation environments (such as Tinkercad), a hardware implementation should utilize an **external 5V DC power supply rated for at least 2A**. When employing an external supply, it is imperative to **tie the external ground (GND) to the Arduino ground (GND)** to establish a unified reference plane for clean PWM signaling.

---

## 🔌 Wiring Diagram

Digital input/output pins that natively support hardware PWM have been mapped out to prevent signal jitter and guarantee exact angular displacement:

1. **Servo Motor 1:**
   * Signal Wire (Yellow/Orange) ➡️ **Digital Pin 9 (PWM)** on Arduino.
   * Power Wire (Red) ➡️ Positive (+) Rail on Breadboard.
   * Ground Wire (Brown/Black) ➡️ Negative (-) Rail on Breadboard.

2. **Servo Motor 2:**
   * Signal Wire (Yellow/Orange) ➡️ **Digital Pin 10 (PWM)** on Arduino.
   * Power Wire (Red) ➡️ Positive (+) Rail on Breadboard.
   * Ground Wire (Brown/Black) ➡️ Negative (-) Rail on Breadboard.

3. **Servo Motor 3:**
   * Signal Wire (Yellow/Orange) ➡️ **Digital Pin 11 (PWM)** on Arduino.
   * Power Wire (Red) ➡️ Positive (+) Rail on Breadboard.
   * Ground Wire (Brown/Black) ➡️ Negative (-) Rail on Breadboard.

4. **Servo Motor 4:**
   * Signal Wire (Yellow/Orange) ➡️ **Digital Pin 6 (PWM)** on Arduino.
   * Power Wire (Red) ➡️ Positive (+) Rail on Breadboard.
   * Ground Wire (Brown/Black) ➡️ Negative (-) Rail on Breadboard.

---

## 🚀 How to Run & Use

### A. Physical Hardware Implementation:
1. Set up your hardware components according to the **Wiring Diagram** layout detailed above.
2. Launch the **Arduino IDE** on your computer.
3. Ensure the standard `<Servo.h>` library is available (included by default with the Arduino core package).
4. Copy the complete source code from your `Project_Code.ino` file and paste it into the IDE workspace.
5. Connect your Arduino Uno to your PC via a USB cable, choose the matching COM Port and select "Arduino Uno" under Board settings.
6. Click **Upload** to compile and flash the firmware.
7. Upon successful deployment, observe the servos executing the simultaneous 2-second sweep sequence, followed by an immediate lock at 90 degrees.

### B. Virtual Simulation Execution:
1. Navigate to **Tinkercad Circuits** or **Wokwi**.
2. Assemble an identical circuit configuration featuring an Arduino Uno, a breadboard, and 4 micro servos.
3. Wire the virtual circuit as instructed in the wiring blueprint.
4. Copy and insert the provided Arduino C++ script into the simulation environment's code editor.
5. Click **Start Simulation**.

---

## 🎥 Media & Documentation

* **Interactive Tinkercad Simulation Link:** [Click here to view and run the live schematic on Tinkercad](https://www.tinkercad.com/things/ahTlGQhxtzC-multi-servo-sweep-hold-system?sharecode=BphMW_4GQIAqwUrX1roOdkkti5bM3Lq0ZpofMgiG0Ko)
* **Circuit Wiring Schematic Overview:**
  ![wiring setup](https://raw.githubusercontent.com/YourGitHubUsername/YourRepoName/main/Multi-Servo%20Sweep%20%26%20Hold%20System%20pic%202.png)
* **Simulation Workspace & Code Execution:**
  ![simulation run](https://raw.githubusercontent.com/YourGitHubUsername/YourRepoName/main/Multi-Servo%20Sweep%20%26%20Hold%20System%20pic%203.png)
