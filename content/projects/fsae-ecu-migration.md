---
title: "FSAE ECU Migration: Motec M150 Integration"
date: 2024-05-20
summary: "Lead the transition from a PE3 to a Motec M150 ECU, implemented Volumetric Efficiency tuning and validated via dyno testing."
featured_image: "/images/M1_tune1-5.png" 
---

## Project Overview
I led the effort to migrate of NovaRacing's primary Electronic control system from a simple PE3 electronic Control Unit (ECU) to a fully-capable Motec M150. This upgrade was critical to unlock effective data logging, finer control resolution, and a more robust fuel model for competition. The M150 was selected for its
1.  Custom firmware Support: Allowed for user-defined algorithms.
2.	Telemetry Capabilities: Excellent data logging and visualization in real time.
3.	I/O Density: Large number of inputs and outputs
4.	Volumetric Efficiency (VE) Modeling: Transitioned from simple lookup tables to dynamic airflow calculations

{{< figure src="/images/m150.png" caption="M150 ECU" class="w-50">}}

## Technical Implementation

### 1. Hardware Integration
The migration required an overhaul of the engine harness. I redesigned the wiring harness in order to work with the new pinout and configured the ECU with sensor calibrations and I/O control. This involved:
* **Sensor Integration:** Calibrating and wiring pressure, temperature, and position sensors.
* **Ignition Timing:** Using a timing light to mechanically verify and set the digital base timing offset, ensuring synchronization between the ECU and physical engine cycle.

### 2. Control Strategy: Alpha-N to Volumetric Efficiency
{{< figure src="/images/fuel_calc.png">}}
The most challenging engineering effort was shifting our fuel modeling strategy.
* **Legacy System:** Relied on "Alpha-N" (Throttle Pedal vs. RPM), which offers limited precision under varying load conditions.
* **New System:** Implemented a **Volumetric Efficiency (VE)** model. This required modeling the airflow and fuel through the engine. This shift allows the engine to adapt better to environmental changes (temperature, transients) without manual re-tuning.
{{< figure src="/images/dyno-etc.png" class="w-50" caption="Custom engine dyno for simple testing">}}


### 3. Validation & Tuning
![car on dyno](/images/car_on_dyno.jpg)

* **Chassis Dyno:** Once the base map was established, a professional chassis dyno was used to optimize the ignition and fuel tables for peak torque and reliability.

![power curve](/images/power-curve.png)

## Key Challenges Solved

**Legacy Debt & Documentation**
The transition involved learning alot about how engines work and the absolute necessity for accurate control systems for proper engine performance. I learned about the necessity of documentation and how any wholes in it can cause hours of time spent troubleshooting simple problems.

**The Learning Curve**
Moving to Motec required mastering a new software ecosystem. I had to bridge the gap between theoretical control systems and practical application, specifically regarding the complex math behind the Volumetric Efficiency and fuel model.

## Outcome
This was my first major project as a member of NovaRacing, which took almost a full year of hardwork before it was finally finished. With the help of an upperclassman mentor, I started out learning about the different components of the car by assembling the fuel and cooling systems on the dyno, followed by rewiring the harness to match the MoTeC pinout. Eventually, I took lead as we moved into the more theoretical, complex engine modeling part. After around 12 months of hardwork, the system was successfully integrated and tuned. Overall, it was great learning experience, that allowed me to earn a leadership position in NovaRacing. This project greatly developed my skills in:
* **Learning complex technical skills from the ground up**
* **Data Analysis & Engine Tuning**
* **Wiring and pinouts**
* **Control Theory Application**

*Things you could include:*
> - *Talk about the improvement in the data collection process*
> - *Talk about the horsepower gains with the new tune*
> - *Lambda reliability graphs?*