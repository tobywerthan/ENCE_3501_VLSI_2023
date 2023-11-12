# Lab 6: DC to DC Converter

Toby Werthan

11/12/2023

ENCE 3501

## Table of Contents
1. [Introduction](#introduction)
2. [Charge Pump](#nand)
    1. [Schematic](#nandSchem)
    2. [Simulation](#nandSim)
3. [Ring Oscillator](#not)
    1. [Schematic](#notSchem)
    2. [Simulation](#notSim)
4. [Voltage Regulator](#xor)
    1. [Schematic](#xorSchem)
    2. [Simulation](#xorSim)
5. [DC to DC Regulator](#fulladder)
    1. [Schematic](#fulladderSchem)
    2. [Simulation](#fulladderSim)
6. [Conclusion](#conclusion)

*Note: If images are hard to view, please click on them. A new tab will open, displaying the full-size image.*
    
<h2>Introduction</h2>  <a name="introduction"></a>

<dl><dd>

<p>
   The purpose of this lab was to create a DC-to-DC regulator in Electric VLSI. This lab only outlines the schematics and simulations of the individual components that make up the DC-to-DC regulator. The components outlined include a three-stage charge pump, a ring oscillator with an enabling capability, and a voltage regulator that works as a comparator. 
</p>

<p align="center">
  <img width="900" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/e1b34333-5534-4a7e-a500-9dc2bd5943bc">
</p>

<p align="center">
    Figure 1 (Provided schematic of the DC-to-DC Regulator)
</p>

</dd><dl>

<h2> Charge Pump </h2> <a name="nand"></a>

<dl><dd><h3>Schematic</h3> <a name="nandSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The first component created for the DC-to-DC regulator was a three-stage charge pump. This schematic will ideally have an output voltage three times that of the input. In this case, the input voltage is one volt, so the output of this schematic would be three volts.
</p>

<p align="center">
  <img width="850" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/34305b8e-0911-408d-b24a-5ed6cedf9bc3">
</p>

<p align="center">
    Figure 2 (Schematic of the charge pump in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the charge pump. 
</p>

<p align="center">
  <img width="300" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/42c24cbd-69c0-46a0-bb0c-96e24d083bd7">
</p>
<p align="center">
    Figure 3 (Icon generated from the charge pump schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="nandSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The simulation of the charge pump tests the output voltage. Two pulse waves are fed into the charge pump that are out of phase from each other by 90 degrees. The inout voltage is also 1v. A transient is recorded of the output. 
</p>
    
<p align="center">
  <img width="900" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/cd6ecc9d-3c43-4293-9798-0b4052aae2c3">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the charge pump in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 DC 1
        vosc osc 0 pulse(0 1 0 1p 1p 0.025 0.05)
        vosc2 osc2 0 pulse(0 1 0.025 1p 1p 0.025 0.05)
        .tran 0 1000 1m
<p align="center">
    Figure 7 (Spice simulation code for the charge pump)
</p>

<p>
    The results of the simulation were successful in that the input voltage is increased significantly. However, as mentioned before, the ideal output voltage would be three volts. The low output seen in this result is most likely due to voltage loss calculations done in Electric VLSI. To remedy the low output voltage, more stages can be added to the charge pump's circuit allowing for the voltage to charge even more over time. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/23b8cb12-79da-4a20-861b-d4928ad37bd2">
</p>

<p align="center">
    Figure 8 (Simulation results of the charge pump in LTSpice)
</p>
    
</dd></dl></dd></dl>

<h2> Ring Oscillator </h2> <a name="not"></a>

<dl><dd><h3>Schematic</h3> <a name="notSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The next component created for the DC-to-DC regulator was the ring oscillator. This circuit will provide two pulse waves that are offset from each other by 90 degrees. This will serve as the input to the charge pump. Ideally, this will allow the charge pump to work without the need for simulated inputs. 
</p>

<p align="center">
  <img width="900" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d9f8f5bc-e984-4c6b-bbcc-9f5ed3cb6994">
</p>
<p align="center">
    Figure 12 (Schematic of the ring oscillator in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the ring oscillator. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/38e16430-6d38-4873-8fb4-4c6c519ced8d">
</p>
<p align="center">
    Figure 13 (Icon generated from the ring oscillator schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="notSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The simulation of the ring oscillator tests that the output consists of two square waves and their offset. The input voltage is set to one volt, and the enable pin is also set to 1v. The transient of the circuit is then recorded. 
</p>
    
<p align="center">
  <img width="1000" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/f568cd0d-a0c1-4356-aa48-9e244c2535df">
</p>
<p align="center">
    Figure 16 (Simulation schematic of the ring oscillator in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 1
        ven en 0 dc 1
        .tran 0 10
<p align="center">
    Figure 17 (Spice simulation code for the ring oscillator)
</p>

<p>
    The results of the simulation were successful because the ring oscillator produces two square waves offset by 90 degrees when enabled.  
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/cd568de1-1724-47e0-8d1c-4ba29473f9cc">
</p>
<p align="center">
    Figure 18 (Simulation results of the ring oscillator in LTSpice)
</p>

</dd></dl></dd></dl>

<h2> Voltage Regulator </h2> <a name="xor"></a>

<dl><dd><h3>Schematic</h3> <a name="xorSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The last component needed for the DC=to-DC regulator is a voltage regulator or comparator. This circuit will monitor the output of the charge pump and will control the enable pin of the oscillator depending on the charge pump's value. 
</p>

<p align="center">
  <img width="900" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/7c0d92c7-6ec9-40d0-9005-36d0c6d85327">
</p>
<p align="center">
    Figure 19 (Schematic of the voltage regulator in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the voltage regulator. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/dde9b9c1-c6c0-49d1-98de-624d2a989074">
</p>
<p align="center">
    Figure 20 (Icon generated from the voltage regulator schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="xorSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The simulation of the voltage regulator tests that the regulator will activate when its input goes below one volt. The input voltage of the circuit is set to one volt. A sine wave is applied to the input of the regulator and the circuit transient is recorded. 
</p>
    
<p align="center">
  <img width="900" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/4676facc-8625-40a3-927c-ebfce46a723e">
</p>
<p align="center">
    Figure 23 (Simulation schematic of the voltage regulator in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 1
        vout vout 0 sin(1.5 1.5 50)
        .tran 0 1
<p align="center">
    Figure 24 (Spice simulation code for the voltage regulator)
</p>

<p>
    The results of the simulation were successful in the sense that the circuit did output a high voltage once the input voltage reached a certain level. However, ideally, the circuit would output one volt when the input voltage reaches below 0.5 volts. This means that the circuit's values need some adjustment. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/6f17f31c-f55a-4f8a-a859-8f4715f0b8d1">
</p>
<p align="center">
    Figure 25 (Simulation results of the voltage regulator in LTSpice)
</p>

</dd></dl></dd></dl>

<h2> DC to DC Converter </h2> <a name="fulladder"></a>

<dl><dd><h3>Schematic</h3> <a name="fulladderSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The provided schematic shows the ring oscillator feeding into the charge pump. The charge pump's output is then brought into the comparator. The output of the comparator then controls the enable of the ring oscillator. This will ideally keep the output voltage from the charge pump at or below 1v. 
</p>

<p align="center">
  <img width="900" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/b05d288e-c591-4e32-985f-7a0a62349927">
</p>
<p align="center">
    Figure 29 (Schematic of the DC-to-DC regulator in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="fulladderSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The simulation of the DC-to-DC regulator tests that the output voltage remains at, or below one volt. The input voltage is set to one volt. The enable of the oscillator is set to one volt and the transient is recorded. 
</p>

<p align="center">
  <img width="900" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0f511a7c-adb7-44e5-8a13-b45405e5ebd0">
</p>
<p align="center">
    Figure 33 (Simulation schematic of the DC-to-DC regulator in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 1
        ven en 0 dc 1
        .tran 0 10
<p align="center">
    Figure 34 (Spice simulation code for the DC-to-DC regulator)
</p>

<p>
    The results of the simulation appear to be successful. The output voltage of the circuit does not seem to be exceeding one volt and the output of the comparator is one volt. However, if the charge pump exceeds 1v, the circuit will not work as expected. This documentation does not provide a working circuit for the DC-to-DC regulator, a new solution needs to be procured.  
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0f383b13-c002-4385-80e5-9f9f1412c475">
</p>
<p align="center">
    Figure 35 (Simulation results of the DC-to-DC regulator)
</p>

</dd></dl></dd></dl>

<h2>Conclusion</h3>  <a name="conclusion"></a>

<p>
    Lab 6 explored the creation of a DC-to-DC regulator. While the circuit is not fully functional, this lab provided a window into how self-sustaining circuits are designed and implemented. This also highlights how complex and difficult it can be to build a system like this in ELectric VLSI. 
</p>

