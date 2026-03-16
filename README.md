# Non-Inverting Amplifier Design & Physical Implementation

## Overview
This project focuses on the theoretical modeling, simulation, and physical Printed Circuit Board (PCB) implementation of a non-inverting amplifier. The circuit is designed to provide stable voltage gain without phase inversion, acting as a foundational building block for analog signal processing systems.

## Tools & Components
* **Simulation:** LTspice XVII
* **PCB Design:** Proteus 8
* **Active Component:** OP07 Operational Amplifier
* **Passive Components:** WH138-B20K Potentiometer (for variable gain tuning), 1kΩ Resistor.

## System Architecture
The core of the design utilizes a negative feedback network to establish a predictable closed-loop voltage gain, defined by the fundamental formula:
**Av = 1 + (Rf / R)**
Where `R` is fixed at 1kΩ, and `Rf` is adjusted via the potentiometer to achieve the desired voltage gain.

## Simulation Results
Transient analysis was performed to verify the circuit's behavior under different gain configurations:
* **Av = 10:** With an input pulse of 2.5mV, the output correctly scaled to approximately 25mV.
* **Av = 20:** The output successfully reached 50mV in phase with the input.

![image](https://github.com/Hudo1501/Non-Inverting-Amplifier/blob/432b2167275fe33683ba7dd7531489f80e0ca5e6/gain_10.jpg)
![image](https://github.com/Hudo1501/Non-Inverting-Amplifier/blob/432b2167275fe33683ba7dd7531489f80e0ca5e6/gain_20.jpg)

## Hardware Implementation & 🔧 Troubleshooting
The theoretical design was translated into a physical PCB. During the manual fabrication process, a layout transfer error occurred (the non-mirrored bottom-layer design was used, which caused the component pins to obstruct the traces under the IC). 

**Engineering Workaround:** Standard through-hole soldering became impossible. To overcome this issue, an unconventional hardware debugging technique was implemented: specific IC pins were lifted, and point-to-point wired connections were established directly to their corresponding traces to bypass the obstruction and complete the circuit. 
    
![image](https://github.com/Hudo1501/Non-Inverting-Amplifier/blob/cdb02b57ecdb3237182d4bdc701473717ec6fd92/pcb_layout.png)
![image](https://github.com/Hudo1501/Non-Inverting-Amplifier/blob/cdb02b57ecdb3237182d4bdc701473717ec6fd92/phy_PCB.jpg)

## Experimental Results
Hardware measurements using a Tektronix Digital Oscilloscope validated the simulation data. The output waveforms remained perfectly in-phase with the input pulses, and the amplitude scaled accurately with the potentiometer adjustments, proving the real-world reliability of the theoretical model.


![image](https://github.com/Hudo1501/Non-Inverting-Amplifier/blob/758092200149bb3a9d7e30790f3e4e014da0c7f5/oscilloscope_g10.jpg)
![image](https://github.com/Hudo1501/Non-Inverting-Amplifier/blob/758092200149bb3a9d7e30790f3e4e014da0c7f5/oscilloscope_g20.jpg)

## 👨‍💻 My Contribution
As a core team member (Group 5), my responsibilities included:
* **Simulation & Research:** Modeling the circuit in LTspice and conducting extensive transient analyses to verify the Av formulas.
* **Technical Documentation:** Compiling and formatting the comprehensive lab report, detailing the operational characteristics and the practical hardware troubleshooting process.
