---
title: "FSAE ECU Migration: Motec M150 Integration"
date: 2024-05-20
summary: "Leading the transition from a PE3 to a Motec M150 ECU, implementing Volumetric Efficiency tuning and validating via dyno testing."
featured_image: "/images/M1_tune1-5.png" 
---

## Project Overview
As a member of the University Formula team, I led the electrical and controls migration for our competition vehicle. The objective was to replace a legacy PE3 Engine Control Unit (ECU) with a modern Motec M150. This upgrade was critical to unlock advanced data logging, finer control resolution, and a more robust fuel model for competition.

<!-- ![motec m150](/images/m150.png) -->
{{< figure src="/images/m150.png" title="M150 ECU" class="w-50">}}

## Technical Implementation

### 1. Systems Architecture & Wiring
The migration required a complete overhaul of the engine harness. I designed and routed the wiring to integrate the Motec M150 with our sensor suite. This involved:
* **Sensor Integration:** Calibrating and wiring pressure, temperature, and position sensors.
* **Ignition Timing:** Using a timing light to mechanically verify and set the digital base timing offset, ensuring synchronization between the ECU and physical engine cycle.

### 2. Control Strategy: Alpha-N to Volumetric Efficiency
One of the most significant engineering efforts was shifting our fuel modeling strategy.
* **Legacy System:** Relied on "Alpha-N" (Throttle Position vs. RPM), which offers limited precision under varying load conditions.
* **New System:** Implemented a **Volumetric Efficiency (VE)** model. This required calculating the theoretical mass airflow based on engine geometry and manifold pressure, then tuning the efficiency table. This shift allows the engine to adapt better to environmental changes (altitude, temperature) without manual re-tuning.



[Image of car engine schematic]


### 3. Validation & Tuning
![car on dyno](/images/car_on_dyno.jpg)

To validate the system before track testing, I engineered a staged testing environment:
* **Makeshift Dyno:** Assembled a powertrain stand to test startup, idle control, and sensor fidelity in a controlled, static environment.
* **Chassis Dyno:** Once the base map was established, I managed the transition to a professional chassis dyno to optimize the ignition and fuel tables for peak torque and reliability.

## Key Challenges Solved

**Legacy Debt & Documentation**
The transition involved migrating untested and unmaintained code from previous years. I had to reverse-engineer parts of the legacy harness and debug logic errors in the firmware that had not been validated.

**The Learning Curve**
Moving to Motec required mastering a new software ecosystem. I had to bridge the gap between theoretical control systems (learned in class) and practical application, specifically regarding the complex math behind the VE fluid dynamics model.

## Outcome
After 12 months of development, the system was successfully integrated and tuned. The vehicle now runs a fully closed-loop fuel control system with higher reliability and data granularity. This project developed my skills in:
* **Data Analysis & Engine Tuning**
* **Embedded Systems Wiring**
* **Control Theory Application**
* **Project Management (Full lifecycle execution)**