# Buck-Boost Converter Design, Simulation and Hardware Implementation

## Overview

This project presents the design, simulation, and hardware implementation of an inverting Buck Converter developed as part of the EE252 Electrical Machines and Power Electronics Laboratory at IIT Indore.

The converter is designed to operate from a fixed 20 V DC input source and provide a controllable output voltage of 7.5V while delivering 1 A load current with switching frequency of 20kHz. Both Continuous Conduction Mode (CCM) and Discontinuous Conduction Mode (DCM) operations were studied and experimentally verified.

The project includes:

Theoretical design calculations
MATLAB/Simulink simulation
Gate driver implementation using TL494 and TC4428A
Hardware prototype fabrication
Experimental waveform verification

## Project Specifications

| Parameter | Value |
| :--- | :--- |
| Input Voltage | 20 V |
| Output Voltage | 7.5 V |
| Output Current | 1 A |
| Switching Frequency | 20 kHz |
| Converter Type | Buck |
| Inductor | 1 mH |
| Output Capacitor | 470 µF |
| PWM Controller | TL494 |
| Gate Driver | TC4428A |
| Power MOSFET | IRFZ44NPbF |
| Diode | QH08TZ600 |



## Working Principle


The Buck converter (step-down converter) transfers energy from the input DC source to the load by chopping the input voltage using a high-frequency switch (MOSFET). It utilizes an inductor and a capacitor as an energy-storage filter to deliver a smooth, lower DC output voltage.

### MOSFET ON State
* **Diode status:** Reverse-biased (turned OFF).
* **Inductor action:** Connects directly to the input source; stores energy in its magnetic field.
* **Current behavior:** Inductor current rises linearly, supplying energy to both the output capacitor and the load.

### MOSFET OFF State
* **Diode status:** Forward-biased (turned ON), acting as a freewheeling diode.
* **Inductor action:** Disconnects from the source; releases its stored energy to sustain the load current.
* **Current behavior:** Inductor current decreases linearly as energy is delivered to the output.

---

### Voltage Conversion Ratio

The ideal voltage conversion ratio for a Buck converter operating in Continuous Conduction Mode (CCM) is given by:

$$\frac{V_o}{V_{in}} = D$$

Where:
* **$V_o$** = Output Voltage
* **$V_{in}$** = Input Voltage
* **$D$** = Duty Cycle ($0 < D < 1$)



## Gate Driver Design


### TL494 PWM Controller
The TL494 PWM controller is used for generating switching pulses.

Features:

Adjustable duty cycle
Adjustable frequency
Internal oscillator
Dead-time control
Error amplifiers

### TC4428A MOSFET Driver
The TC4428A driver provides:

Fast gate charging
Fast gate discharging
Reduced switching losses
Improved switching performance
The driver board includes:

D-VARY potentiometer for duty cycle control
F-VARY potentiometer for frequency control

MATLAB Simulation
The converter was modeled and simulated in MATLAB Simulink.

### Simulation Objectives


Verify voltage conversion ratio
Observe inductor voltage waveform
Observe diode current waveform
Verify CCM operation
Verify DCM operation

### Simulation Results

Output Voltage
Inductor Voltage
Diode Current
Inductor Current in DCM
Simulation results matched theoretical expectations.

