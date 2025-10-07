# 🚴‍♂️ Child Safety Monitoring – Android/iOS Application

A **MATLAB Simulink–based mobile application** that monitors a child’s safety while riding a bicycle using the phone’s built-in sensors (accelerometer, gyroscope, GPS, microphone, and network connectivity).
The system simulates a **smart bicycle** environment where one phone acts as the **child’s device (sender)** and another as the **parent’s device (receiver)**.

---

## 🧠 Problem Statement

Design and deploy an Android/iOS app for a **smart bicycle** that enables parents to monitor their child’s safety in real time.

The application uses the child’s mobile phone as a **virtual IoT device**, collecting and transmitting sensor data to the parent’s phone for safety alerts and live monitoring.

---

## ⚙️ System Overview

The system consists of two connected mobile devices:

* **Phone A (Sender – Child’s Device)**
  Acts as the IoT-enabled bicycle. It continuously collects and transmits sensor data.

* **Phone B (Receiver – Parent’s Device)**
  Receives data and alerts from Phone A to notify the parent about the child’s activity and safety status.


---

## 📱 Features

### 1. **Fall Detection**

* Continuously monitors accelerometer and gyroscope data.
* Calculates **sum of squared acceleration** to detect falls.
* Filters out false positives (e.g., bumps or braking).
* On fall detection:

  * Plays a **beep alarm** on Phone A.
  * Displays the real-time location on Phone B.
  * Plays a **beep** on Phone B.
  * If the alarm is **not switched off within 5 seconds**:

    * Automatically activates the microphone on Phone A.
    * Starts recording ambient sound.
    * Sends an **SOS alert** (recording ) to Phone B via the internet.

---

### 2. **Boundary Crossing**

* Monitors GPS coordinates to ensure the child stays within a defined safe perimeter.
* When the bicycle crosses the set boundary:

  * Plays an alarm on **Phone A**.
  * Displays the child’s **real-time location** on **Phone B**.
  * Triggers an alert sound on **Phone B**.

---

## 🧩 Implementation Details

* **Platform:** MATLAB Simulink Mobile
* **Target Devices:** Android / iOS
* **Communication:** Internet (mobile data)
* **Sensors Used:**

  * GPS
  * Accelerometer
  * Gyroscope
  * Microphone
  * Antenna/Network

---

## 🔄 Data Flow

1. **Sensor Acquisition (Phone A)**
   Collects real-time accelerometer, gyroscope, and GPS data.

2. **Event Detection**
   Checks for:

   * Sudden acceleration changes → possible fall
   * GPS threshold crossing → boundary breach

3. **Alert Trigger (Phone A)**
   Plays warning sounds and sends data packets to Phone B.

4. **Parent Notification (Phone B)**
   Receives location and alerts.



---

## 🚀 How to Use

1. Open the project in **MATLAB Simulink**.
2. Load the **Sender** model on the child’s phone (Phone A).
3. Load the **Receiver** model on the parent’s phone (Phone B).
4. Connect both devices to the same network or enable mobile internet.
5. Start the simulation — the system will automatically begin monitoring.

---

## 📂 Repository Structure

```
Child-safety-monitoring-system/
│
├── Sender/                 # Simulink model for the child’s device
├── Receiver/               # Simulink model for the parent’s device
├── images/
│   └── simulink_app.png    # System model image
├── README.md               # Project documentation
└── LICENSE                 # License information
```

---

## 🧠 Future Improvements

* Add SMS or WhatsApp integration for SOS alerts


---

## 👨‍💻 Author

**Pratyaksh Bhayre**
