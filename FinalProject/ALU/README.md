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
6. [Further Investigation](#debug)
    1. [Testing in Logisim](#debugLogisim)
    2. [Finding the Problem](#debugProblem)
    3. [Implementing the Solution](#debugSuccess)
7. [Conclusion](#conclusion)

*Note: If images are hard to view, please click on them. A new tab will open, displaying the full-size image.*
    
<h2>Introduction</h2>  <a name="introduction"></a>

<dl><dd>

<p>
   The purpose of this project was to create an Arithmetic Logic Unit in Electric VLSI. This report outlines each component used to construct the ALU as well as their designs. The ALU design is then broken down by schematic and layout with aided visual representations of the circuit. The design is also simulated and tested. 
</p>

<p align="center">
  <img width="900" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/238591f5-ef24-420b-bd58-39ac919c709c">
</p>

<p align="center">
    Figure 1 (Provided schematic of the ALU)
</p>

</dd><dl>







<h2> Inverter </h2> <a name="inv"></a>

<dl><dd><h3>Schematic</h3> <a name="invSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The inverter used in the schematic for the ALU was provided by the "muddLib07.jelib" library provided before the Final Project. The inverter was modeled using the provided spice models, "cmosedu_models.txt". The model used was the P_1u and N_1u transistors because the working voltage of the ALU will be 5 volts. The schematic for the inverter is shown below.  
</p>

<p align="center">
  <img width="550" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/5bb922ef-1923-44da-ac6c-b2d6874ca3e0">
</p>

<p align="center">
    Figure 2 (Schematic of the inverter)
</p>

<p>    
    An icon that is generated from the schematic was also provided with the library. The icon is shown below. 
</p>

<p align="center">
  <img width="450" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/57f695ba-4f2e-45da-8dbf-9267fe0ed5e7">
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
  <img width="300" height="850" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/cb8717a2-b710-472d-8b4f-11deeb986b58">
</p>

<p align="center">
    Figure 4 (Layout of the inverter)
</p>

<p>    
   The 3D view of the inverter is also provided below
</p>

<p align="center">
  <img width="650" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/9c12a270-8409-401f-83cb-aa2e1648b1aa">
</p>
<p align="center">
    Figure 5 (3D View of the inverter)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="invSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The two simulations of the schematic of the inverter test both the logic values as well as the switching point. 
</p>
    
<p align="center">
  <img width="850" height="450" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d8db8074-e71e-4e9f-8a51-d42e433f5b4d">
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
    The result of the simulated logic values of the schematic of the inverter was successful. The input value of the inverter is negated in the output. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/9ef19aca-1a50-4b69-aa80-73de32f4c2e7">
</p>

<p align="center">
    Figure 9 (Schematic simulation of the logic values of the inverter)
</p>

<p>
    The result of the simulated switching point of the schematic of the inverter was successful. The switching point can be seen to be roughly half of 5V. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/dd8d149f-a52d-4efb-86b9-2e15e5a8855d">
</p>

<p align="center">
    Figure 10 (Schematic simulation of the switching point of the inverter)
</p>


<p>
    The two simulations of the layout of the inverter test both the logic values as well as the switching point. 
</p>
    
<p align="center">
  <img width="650" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/8bf1e0f1-418c-487f-aca5-cadcd62afb4c">
</p>

<p align="center">
    Figure 11 (Layout simulation of the inverter)
</p>

<p>
    A snippet of the spice code for the logic value simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        vin d_in 0 pulse(0 5 10n 1n 1n 40n 40n)
        .tran 0 40n
<p align="center">
    Figure 12 (Spice code for the switching point simulation of the inverter)
</p>

<p>
    A snippet of the spice code for the switching point simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        vin d_in 0 dc 5
        .tran 0 40n
<p align="center">
    Figure 13 (Spice code for the logic value simulation of the inverter)
</p>

<p>
    The result of the simulated logic values of the layout of the inverter was successful. The input value of the inverter is negated in the output. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/37e3ceab-4420-41e6-a506-9ebf062794a2">
</p>

<p align="center">
    Figure 14 (Layout simulation of the logic values of the inverter)
</p>

<p>
    The result of the simulated switching point of the layout of the inverter was successful. The switching point can be seen to be roughly half of 5V. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/cd4577ed-5810-41b0-8a5a-74e4e042fc13">
</p>

<p align="center">
    Figure 15 (Layout simulation of the switching point of the inverter)
</p>
    
</dd></dl></dd></dl>






<h2> Multiplexer </h2> <a name="mux"></a>

<dl><dd><h3>Schematic</h3> <a name="muxSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The multiplexer used in the schematic for the ALU was provided by the "muddLib07.jelib" library provided before the Final Project. The multiplexer was modeled using the provided spice models, "cmosedu_models.txt". The model used was the P_1u and N_1u transistors because the working voltage of the ALU will be 5 volts. The schematic for the multiplexer is shown below. 
</p>

<p align="center">
  <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/2d5673c4-5d4f-4d7b-b109-13bb660b9924">
</p>
<p align="center">
    Figure 16 (Schematic of the multiplexer)
</p>

<p>    
    An icon that is generated from the schematic was also provided with the library. The icon is shown below. 
</p>

<p align="center">
  <img width="300" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/5072e7b3-a71a-4c63-9005-a2abe29db949">
</p>
<p align="center">
    Figure 17 (Icon of the multiplexer)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="muxLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The layout of the multiplexer was also provided by the "muddlib07.jelib" library. The layout can viewed below. 
</p>

<p align="center">
  <img width="700" height="700" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/cfd173eb-3860-48b1-81ac-aa3788eca86a">
</p>

<p align="center">
    Figure 18 (Layout of the multiplexer)
</p>

<p>    
   A 3D view of the multiplexer is provided below.
</p>

<p align="center">
  <img width="800" height="650" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/eb4fff30-47b7-4d98-9529-e9d3279536e3">
</p>
<p align="center">
    Figure 19 (3D View of the multiplexer)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="muxSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The simulation of the schematic of the multiplexer tests the logic values of the circuit. 
</p>
    
<p align="center">
  <img width="900" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/c8de572d-4251-44b7-a2e6-4e3cb9b452f3">
</p>
<p align="center">
    Figure 20 (Schematic simulation of the multiplexer)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        vd0 d0 0 pulse(0 5 0 1n 1n 10n 20n)
        vd1 d1 0 pulse(0 5 3n 1n 1n 10n 20n)
        vs s 0 pulse(0 5 6n 1n 1n 10n 20n)
        .tran 0 60n
<p align="center">
    Figure 21 (Spice code for the schematic simulation of the multiplexer)
</p>

<p>
    The result of the simulation was successful. The output of the multiplexer behaves as expected, the result can be seen below. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/ab5a0fe4-f2ca-4628-82e7-e1692de290e0">
</p>

<p align="center">
    Figure 22 (Results of the schematic simulation of the multiplexer)
</p>

<p>
    The simulation of the layout of the multiplexer tests the logic values of the circuit. 
</p>
    
<p align="center">
  <img width="900" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/ded990ef-9f2a-4aac-9566-5fce7e081afb">
</p>
<p align="center">
    Figure 23 (Layout simulation of the multiplexer)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        vd0 d0 0 pulse(0 5 0 1n 1n 10n 20n)
        vd1 d1 0 pulse(0 5 3n 1n 1n 10n 20n)
        vs s 0 pulse(0 5 6n 1n 1n 10n 20n)
        .tran 0 60n
<p align="center">
    Figure 24 (Spice code for the layout simulation of the multiplexer)
</p>

<p>
    The result of the simulation was successful. The output of the multiplexer behaves as expected, the result can be seen below. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/430cfa3d-c3e8-48ec-a2bf-9a28d4852203">
</p>
<p align="center">
    Figure 25 (Results of the layout simulation of the multiplexer)
</p>
    
</dd></dl></dd></dl>






<h2> Full Adder </h2> <a name="fa"></a>

<dl><dd><h3>Schematic</h3> <a name="faSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The full adder used in the schematic for the ALU was provided by the "muddLib07.jelib" library provided before the Final Project. The full adder was modeled using the provided spice models, "cmosedu_models.txt". The model used was the P_1u and N_1u transistors because the working voltage of the ALU will be 5 volts. The schematic for the full adder is shown below. 
</p>

<p align="center">
  <img width="850" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/332a5529-a21f-4889-8a77-c5ba433232db">
</p>
<p align="center">
    Figure 26 (Schematic of the full adder)
</p>

<p>    
    An icon that is generated from the schematic was also provided with the library. The icon is shown below. 
</p>

<p align="center">
  <img width="300" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/26974203-9fa4-4ae2-96be-7ab7ad04df29">
</p>
<p align="center">
    Figure 27 (Icon of the full adder)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="faLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The layout of the full adder was also provided by the "muddlib07.jelib" library. The layout can viewed below. 
</p>

<p align="center">
  <img width="850" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/f136d5f6-5c89-4ebd-9751-f019d4cb8470">
</p>

<p align="center">
    Figure 28 (Layout of the full adder)
</p>

<p>    
   A 3D view of the full adder is provided below.
</p>

<p align="center">
  <img width="850" height="700" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/b857fed4-21a4-40c9-ae94-0cce50d8d0a3">
</p>
<p align="center">
    Figure 29 (3D View of the full adder)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="faSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The simulation of the schematic of the full adder tests the logic values of the circuit. 
</p>
    
<p align="center">
  <img width="900" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/c9bb9451-b1c8-4d70-af72-9af6948b20d0">
</p>
<p align="center">
    Figure 30 (Schematic simulation of the full adder)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        va a 0 pulse(0 5 0 1n 1n 10n 20n)
        vb b 0 pulse(0 5 3n 1n 1n 10n 20n)
        vc c 0 pulse(0 5 6n 1n 1n 10n 20n)
        .tran 0 60n
<p align="center">
    Figure 31 (Spice code for the schematic simulation of the full adder)
</p>

<p>
    The result of the simulation was successful. The output of the full adder behaves as expected, the result can be seen below. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/088a85a9-b7d6-45d3-a4b0-d314b612317d">
</p>

<p align="center">
    Figure 32 (Results of the schematic simulation of the full adder)
</p>

<p>
    The simulation of the layout of the full adder tests the logic values of the circuit. 
</p>
    
<p align="center">
  <img width="900" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/5ff6cab1-8c6c-4275-9898-73721881ff57">
</p>
<p align="center">
    Figure 33 (Layout simulation of the full adder)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        va a 0 pulse(0 5 0 1n 1n 10n 20n)
        vb b 0 pulse(0 5 3n 1n 1n 10n 20n)
        vc c 0 pulse(0 5 6n 1n 1n 10n 20n)
        .tran 0 60n
<p align="center">
    Figure 34 (Spice code for the layout simulation of the full adder)
</p>

<p>
    The result of the simulation was successful. The output of the full adder behaves as expected, the result can be seen below. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/4f9c81cb-7a16-4251-b72c-63f355a9834e3">
</p>
<p align="center">
    Figure 35 (Results of the layout simulation of the full adder)
</p>

    
</dd></dl></dd></dl>






<h2> Controlled Buffer </h2> <a name="buf"></a>

<dl><dd><h3>Schematic</h3> <a name="bufSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The controlled buffer used in the schematic for the ALU was provided by the "muddLib07.jelib" library provided before the Final Project. The controlled buffer was modeled using the provided spice models, "cmosedu_models.txt". The model used was the P_1u and N_1u transistors because the working voltage of the ALU will be 5 volts. The schematic for the controlled buffer is shown below. 
</p>

<p align="center">
  <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/219a3ba6-2c16-4cf3-8acc-f5bbbe529a39">
</p>
<p align="center">
    Figure 36 (Schematic of the controlled buffer)
</p>

<p>    
    An icon that is generated from the schematic was also provided with the library. The icon is shown below. 
</p>

<p align="center">
  <img width="300" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/93c77cea-5a4d-4f50-ab01-22dbd391bf01">
</p>
<p align="center">
    Figure 37 (Icon of the controlled buffer)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="bufLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The layout of the controlled buffer was also provided by the "muddlib07.jelib" library. The layout can viewed below. 
</p>

<p align="center">
  <img width="600" height="850" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/880c2f2e-4725-425c-96fe-e3f0e2d804b6">
</p>

<p align="center">
    Figure 38 (Layout of the controlled buffer)
</p>

<p>    
   A 3D view of the controlled buffer is provided below.
</p>

<p align="center">
  <img width="650" height="750" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/2bc210e0-ca10-49e2-aa48-c5bd385db227">
</p>
<p align="center">
    Figure 39 (3D View of the controlled buffer)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="bufSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The simulation of the schematic of the controlled buffer tests the logic values of the circuit. 
</p>
    
<p align="center">
  <img width="900" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/5d3d2883-9ec4-4f01-b2e3-acf0daeb409e">
</p>
<p align="center">
    Figure 40 (Schematic simulation of the controlled buffer)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        ven en 0 dc 5
        vd d 0 pulse(0 5 0 1n 1n 10n 20n)
        .tran 0 60n
<p align="center">
    Figure 41 (Spice code for the schematic simulation of the controlled buffer)
</p>

<p>
    The result of the simulation was successful. The output of the controlled buffer behaves as expected, the result can be seen below. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/6e72e804-5243-4755-bfe5-216d9e880582">
</p>

<p align="center">
    Figure 42 (Results of the schematic simulation of the controlled buffer)
</p>

<p>
    The simulation of the layout of the controlled buffer tests the logic values of the circuit. 
</p>
    
<p align="center">
  <img width="900" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/db63ebc4-2d1e-4cea-af69-c054418e744e">
</p>
<p align="center">
    Figure 43 (Layout simulation of the controlled buffer)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        ven en 0 dc 5
        vd d 0 pulse(0 5 0 1n 1n 10n 20n)
        .tran 0 60n
<p align="center">
    Figure 44 (Spice code for the layout simulation of the controlled buffer)
</p>

<p>
    The result of the simulation was successful. The output of the controlled buffer behaves as expected, the result can be seen below. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/35c22cf6-f1db-435d-b88f-dc0ea2d531ec">
</p>
<p align="center">
    Figure 45 (Results of the layout simulation of the controlled buffer)
</p>
    
</dd></dl></dd></dl>





<h2> Arithmetic Logic Unit </h2> <a name="alu"></a>

<dl><dd><h3>Schematic</h3> <a name="aluSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The components in the schematic for the ALU were used from the "muddlib07.jelib" library. The schematic is based on the provided ALU schematic. The unit can perform 4-but addition and subtraction and operates on 5V. The schematic can be seen below. 
</p>

<p align="center">
  <img width="950" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/b457ee4b-3312-48ec-bae3-2938ac2ba24b">
</p>
<p align="center">
    Figure 46 (Schematic of the ALU)
</p>


<p>    
    An icon was generated from the schematic of the ALU. The icon can be seen below. 
</p>

<p align="center">
  <img width="700" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/66e677c6-47ec-47ac-a5aa-e8958d9fc330">
</p>
<p align="center">
    Figure 47 (Icon of the ALU)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="aluLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The layout of the ALU consists of four sections that each pertain to the calculation of one of the output bits. Each section includes an inverter, a 2x1 multiplexer, a full adder, and a controlled buffer. Power rails are also lined through individual components and the entire circuit for easy access. The exports for the ALU are also located in such a way that wiring them to a pad will both be easier and intuitive. The layout of the ALU can be seen below.  
</p>

<p align="center">
  <img width="850" height="900" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/82082160-6653-43df-bf61-3d4faa32da0d">
</p>

<p align="center">
    Figure 48 (Layout of the ALU)
</p>

<p>    
   A 3D view of the ALU is provided below.
</p>

<p align="center">
  <img width="900" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0ff3515c-3751-4b1b-9259-d756a115ea5c">
</p>
<p align="center">
    Figure 49 (3D View of the ALU)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="aluSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The simulation of the schematic of the ALU tests the logic values of the circuit. 
</p>
    
<p align="center">
  <img width="900" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/1b54cb91-bd97-4bff-ab31-1eecbb19320b">
</p>
<p align="center">
    Figure 50 (Schematic simulation of the ALU)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        ven en 0 dc 5
        vop op 0 pulse(0 5 5 1p 1p 5 10)
        vB[0] B[0] 0 dc 5
        vB[1] B[1] 0 dc 0
        vB[2] B[2] 0 dc 0
        vB[3] B[3] 0 dc 5
        vA[0] A[0] 0 dc 5
        vA[1] A[1] 0 dc 5
        vA[2] A[2] 0 dc 0
        vA[3] A[3] 0 dc 0
        .tran 0 10
<p align="center">
    Figure 51 (Spice code for the schematic simulation of the ALU)
</p>

<p>
    The result of the simulation may or may not be successful. Upon inspection, the output of the ALU schematic simulation seemed to be incorrect. However, after double and triple-checking the correctness of the ALU circuit, no issue was found. This has led me to believe that I have either missed something when debugging the schematic or that I have misinterpreted the simulation results. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/68571355-1fcd-4c77-992e-64040b0cb3df">
</p>

<p align="center">
    Figure 52 (Results of the schematic simulation of the ALU)
</p>

<p>
    The simulation of the layout of the ALU tests the logic values of the circuit. 
</p>
    
<p align="center">
  <img width="900" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/b24f8432-d780-4387-af63-b99f17366f33">
</p>
<p align="center">
    Figure 53 (Layout simulation of the ALU)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include cmosedu_models.txt
        
        vdd vdd 0 dc 5
        ven en 0 dc 5
        vop op 0 pulse(0 5 5 1p 1p 5 10)
        vB[0] B[0] 0 dc 5
        vB[1] B[1] 0 dc 0
        vB[2] B[2] 0 dc 0
        vB[3] B[3] 0 dc 5
        vA[0] A[0] 0 dc 5
        vA[1] A[1] 0 dc 5
        vA[2] A[2] 0 dc 0
        vA[3] A[3] 0 dc 0
        .tran 0 10
<p align="center">
    Figure 54 (Spice code for the layout simulation of the ALU)
</p>

<p>
    The results of the simulation were the same as the schematic. While it is unclear if the schematic is correct, the layout matches the topology and simulates in the same fashion as the schematic. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/57a4d8c4-41b6-4397-baf3-27199b23fe75">
</p>
<p align="center">
    Figure 55 (Results of the layout simulation of the ALU)
</p>

</dd></dl></dd></dl>







<h2> Further Investigation </h2> <a name="debug"></a>

<dl><dd><h3>Testing in Logisim</h3> <a name="debugLogisim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    To further understand what is going on with the seemingly dysfunctional ALU created in ELectric, an ALU was created in Logisim. This will help debug the issues that are present in the circuit created in Electric. 
</p>

<p align="center">
  <img width="950" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/b4066f7c-9a75-4d56-818e-9654b4e6a1a9">
</p>
<p align="center">
    Figure 46 (Schematic of the ALU created in Logisim)
</p>


<p>    
    When comparing the schematic from Electric to the schematic in Logisim it's clear that there is an issue. The inputs are flipped for that multiplexer responsible for the two's complement carry bit. This would indicate that the simulation results in Electric VLSI were misinterpreted.
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Finding the Problem</h3> <a name="debugProblem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    In the Electric design, if the AddSub input is set to high, addition is performed. While this is definitely one of the issues, it is not the full story. When interpreting the simulation inputs and results, the index of 0 was treated as the least significant bit. In reality, the least significant bit has an index of 3. 
</p>
<p>    
    A flowchart of the ALU's ideal operation now that there is a better understanding of both the mistakes in the Electric schematic and layout as well as the misinterpretation of the simulation results. 
</p>

<p align="center">
  <img width="950" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/defaa911-6561-43c3-aa15-ae4bfde0ca2f">
</p>
<p align="center">
    Figure 46 (Flowchart of the ALU operation)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Implementing the Solution</h3> <a name="debugSuccess"></a></dd></dl> 

<dl><dd><dl><dd>
    


</dd></dl></dd></dl>







<h2>Conclusion</h3>  <a name="conclusion"></a>

<p>
    The goal of this final project was the create a functioning ALU in Electric VSLI. It is unclear if the results of the simulations are correct or not. If they are, the layout matches the schematic, so the ALU will have been successfully constructed. This project combined many different aspects not only learned in the VLSI course, but also in our degree as a whole from digital design, circuits, and all the way to microprocessors.
</p>


