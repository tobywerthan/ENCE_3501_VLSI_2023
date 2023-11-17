# Final Project: Arithmetic Logic Unit

Toby Werthan

11/17/2023

ENCE 3501

## Table of Contents
1. [Introduction](#introduction)
2. [Inverter](#inv)
    1. [Schematic](#invSchem)
    2. [Layout](#invLay)
    3. [Simulation](#invSim)
3. [Multiplexer](#mux)
    1. [Schematic](#muxSchem)
    2. [Layout](#muxLay)
    3. [Simulation](#muxSim)
4. [Full Adder](#fa)
    1. [Schematic](#faSchem)
    2. [Layout](#faLay)
    3. [Simulation](#faSim)
5. [Controlled Buffer](#buf)
    1. [Schematic](#bufSchem)
    2. [Layout](#bufLay)
    3. [Simulation](#bufSim)
6. [Arithmetic Logic Unit](#alu)
    1. [Schematic](#aluSchem)
    2. [Layout](#aluLay)
    3. [Simulation](#aluSim)
7. [Conclusion](#conclusion)

*Note: If images are hard to view, please click on them. A new tab will open, displaying the full-size image.*
    
<h2>Introduction</h2>  <a name="introduction"></a>

<dl><dd>

<p>
   The purpose of this lab was to create a DC-to-DC regulator in Electric VLSI. This lab only outlines the schematics and simulations of the individual components that make up the DC-to-DC regulator. The components outlined include a three-stage charge pump, a ring oscillator with an enabling capability, and a voltage regulator that works as a comparator. 
</p>

<p align="center">
  <img width="900" height="500" src="">
</p>

<p align="center">
    Figure 1 (Provided schematic of the DC-to-DC Regulator)
</p>

</dd><dl>







<h2> Inverter </h2> <a name="inv"></a>

<dl><dd><h3>Schematic</h3> <a name="invSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The inverter used in the schematic for the ALU was provided by the "muddLib07.jelib" library provided before the Final Project. The inverter was modeled using the provided spice models, "cmosedu_models.txt". The model used was the P_1u and N_1u transistors because the working voltage of the ALU will be 5 volts. The schematic for the inverter is shown below.  
</p>

<p align="center">
  <img width="850" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/5bb922ef-1923-44da-ac6c-b2d6874ca3e0">
</p>

<p align="center">
    Figure 2 (Schematic of the inverter)
</p>

<p>    
    An icon that is generated from the schematic was also provided with the library. The icon is shown below. 
</p>

<p align="center">
  <img width="300" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/57f695ba-4f2e-45da-8dbf-9267fe0ed5e7">
</p>
<p align="center">
    Figure 3 (Icon of the inverter)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="invLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The layout of the inverter was also provided by the "muddlib07.jelib" library. The layout can viewed below. 
</p>

<p align="center">
  <img width="850" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/cb8717a2-b710-472d-8b4f-11deeb986b58">
</p>

<p align="center">
    Figure 2 (Layout of the inverter)
</p>

<p>    
   The 3D view of the inverter is also provided below
</p>

<p align="center">
  <img width="300" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/9c12a270-8409-401f-83cb-aa2e1648b1aa">
</p>
<p align="center">
    Figure 3 (3D View of the inverter)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="invSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The two simulations of the schematic of the inverter test both the logic values as well as the switching point. 
</p>
    
<p align="center">
  <img width="900" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d8db8074-e71e-4e9f-8a51-d42e433f5b4d">
</p>

<p align="center">
    Figure 6 (Schematic simulation of the inverter)
</p>

<p>
    A snippet of the spice code for the logic value simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        vin d_in 0 pulse(0 5 10n 1n 1n 40n 40n)
        .tran 0 40n
<p align="center">
    Figure 7 (Spice code for the switching point simulation of the inverter)
</p>

<p>
    A snippet of the spice code for the switching point simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        vin d_in 0 dc 5
        .tran 0 40n
<p align="center">
    Figure 8 (Spice code for the logic value simulation of the inverter)
</p>

<p>
    The result of the simulated logic values of the schematic of the inverter were successful. The input value of the inverter is negated in the output. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/9ef19aca-1a50-4b69-aa80-73de32f4c2e7">
</p>

<p align="center">
    Figure 8 (Schematic simulation of the logic values of the inverter)
</p>

<p>
    The result of the simulated switching point of the schematic of the inverter was successful. The switching point can be seen to be roughly half of 5V. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/dd8d149f-a52d-4efb-86b9-2e15e5a8855d">
</p>

<p align="center">
    Figure 8 (Schematic simulation of the switching point of the inverter)
</p>


<p>
    The two simulations of the layout of the inverter test both the logic values as well as the switching point. 
</p>
    
<p align="center">
  <img width="900" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/8bf1e0f1-418c-487f-aca5-cadcd62afb4c">
</p>

<p align="center">
    Figure 6 (Layout simulation of the inverter)
</p>

<p>
    A snippet of the spice code for the logic value simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        vin d_in 0 pulse(0 5 10n 1n 1n 40n 40n)
        .tran 0 40n
<p align="center">
    Figure 7 (Spice code for the switching point simulation of the inverter)
</p>

<p>
    A snippet of the spice code for the switching point simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        vin d_in 0 dc 5
        .tran 0 40n
<p align="center">
    Figure 8 (Spice code for the logic value simulation of the inverter)
</p>

<p>
    The result of the simulated logic values of the layout of the inverter was successful. The input value of the inverter is negated in the output. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/37e3ceab-4420-41e6-a506-9ebf062794a2">
</p>

<p align="center">
    Figure 8 (Layout simulation of the logic values of the inverter)
</p>

<p>
    The result of the simulated switching point of the layout of the inverter was successful. The switching point can be seen to be roughly half of 5V. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/cd4577ed-5810-41b0-8a5a-74e4e042fc13">
</p>

<p align="center">
    Figure 8 (Layout simulation of the switching point of the inverter)
</p>
    
</dd></dl></dd></dl>






<h2> Multiplexer </h2> <a name="mux"></a>

<dl><dd><h3>Schematic</h3> <a name="muxSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    SCHEMATIC DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (SCHEMATIC TITLE)
</p>

<p>    
    ICON DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (ICON TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="muxLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    LAYOUT DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (LAYOUT TITLE)
</p>

<p>    
   3D DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (3D TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="muxSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    SIMULATION DESCRIPTION
</p>
    
<p align="center">
  <img width="900" height="600" src="">
</p>
<p align="center">
    Figure 6 (SIMULATION TITLE)
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
    Figure 7 (SPICE CODE TITLE)
</p>

<p>
    SIM RESULT DESCRIPTION
</p>

<p align="center">
  <img width="1500" height="500" src="">
</p>

<p align="center">
    Figure 8 (RESULT TITLE)
</p>
    
</dd></dl></dd></dl>






<h2> Full Adder </h2> <a name="fa"></a>

<dl><dd><h3>Schematic</h3> <a name="faSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    SCHEMATIC DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (SCHEMATIC TITLE)
</p>

<p>    
    ICON DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (ICON TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="faLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    LAYOUT DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (LAYOUT TITLE)
</p>

<p>    
   3D DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (3D TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="faSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    SIMULATION DESCRIPTION
</p>
    
<p align="center">
  <img width="900" height="600" src="">
</p>
<p align="center">
    Figure 6 (SIMULATION TITLE)
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
    Figure 7 (SPICE CODE TITLE)
</p>

<p>
    SIM RESULT DESCRIPTION
</p>

<p align="center">
  <img width="1500" height="500" src="">
</p>

<p align="center">
    Figure 8 (RESULT TITLE)
</p>
    
</dd></dl></dd></dl>






<h2> Inverter </h2> <a name="buf"></a>

<dl><dd><h3>Schematic</h3> <a name="bufSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    SCHEMATIC DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (SCHEMATIC TITLE)
</p>

<p>    
    ICON DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (ICON TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="bufLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    LAYOUT DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (LAYOUT TITLE)
</p>

<p>    
   3D DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (3D TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="bufSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    SIMULATION DESCRIPTION
</p>
    
<p align="center">
  <img width="900" height="600" src="">
</p>
<p align="center">
    Figure 6 (SIMULATION TITLE)
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
    Figure 7 (SPICE CODE TITLE)
</p>

<p>
    SIM RESULT DESCRIPTION
</p>

<p align="center">
  <img width="1500" height="500" src="">
</p>

<p align="center">
    Figure 8 (RESULT TITLE)
</p>
    
</dd></dl></dd></dl>






<h2> Inverter </h2> <a name="alu"></a>

<dl><dd><h3>Schematic</h3> <a name="aluSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    SCHEMATIC DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (SCHEMATIC TITLE)
</p>

<p>    
    ICON DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (ICON TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="aluLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    LAYOUT DESCRIPTION
</p>

<p align="center">
  <img width="850" height="550" src="">
</p>

<p align="center">
    Figure 2 (LAYOUT TITLE)
</p>

<p>    
   3D DESCRIPTION
</p>

<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">
    Figure 3 (3D TITLE)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="aluSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    SIMULATION DESCRIPTION
</p>
    
<p align="center">
  <img width="900" height="600" src="">
</p>
<p align="center">
    Figure 6 (SIMULATION TITLE)
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
    Figure 7 (SPICE CODE TITLE)
</p>

<p>
    SIM RESULT DESCRIPTION
</p>

<p align="center">
  <img width="1500" height="500" src="">
</p>

<p align="center">
    Figure 8 (RESULT TITLE)
</p>
    
</dd></dl></dd></dl>






<h2>Conclusion</h3>  <a name="conclusion"></a>

<p>
    CONCLUSION
</p>


