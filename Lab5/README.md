# Lab 5: CMOS Full Adder

Toby Werthan

11/3/2023

ENCE 3501

## Table of Contents
1. [Introduction](#introduction)
2. [NAND](#nand)
    1. [Schematic](#nandSchem)
    2. [Layout](#nandLay)
    3. [Simulations](#nandSim)
3. [NOT](#not)
    1. [Schematic](#notSchem)
    2. [Layout](#notLay)
    3. [Simulations](#notSim)
3. [XOR](#xor)
    1. [Schematic](#xorSchem)
    2. [Layout](#xorLay)
    3. [Simulations](#xorSim)
3. [Full Adder](#fulladder)
    1. [Schematic](#fulladderSchem)
    2. [Layout](#fulladderLay)
    3. [Simulations](#fulladderSim)
4. [Conclusion](#conclusion)

*Note: If images are hard to view, please click on them. A new tab will open, displaying the full-size image.*
    
<h2>Introduction</h2>  <a name="introduction"></a>

<dl><dd>

<p>
   The purpose of this lab was to create a Full Adder using NAND, NOT, and XOR gates. Each gate was created and simulated in Electric VLSI. Each gate was constructed using NMOS, PMOS, NWell, and PWell components provided in the standard library. 
</p>

<p align="center">
  <img width="900" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/27473dcb-9bbf-484a-90b9-dddcc6808fa9">
</p>
<p align="center">
    Figure 1 (Provided schematic of the Full Adder)
</p>

</dd><dl>

<h2> NAND </h2> <a name="nand"></a>

<dl><dd><h3>Schematic</h3> <a name="nandSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    A NAND gate was created in Electric VLSI. This will be used to construct the Full Adder in order to complete the lab. The schematic for the NAND gate can be seen in Figure 2.
</p>

<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/f642b1fe-d95a-4673-abd2-294617d220da">
</p>
<p align="center">
    Figure 2 (Schematic of the NAND gate in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the NAND gate. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/c0a8b634-59cf-4933-a59c-ff557f1db653">
</p>
<p align="center">
    Figure 3 (Icon generated from the NAND schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="nandLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The layout was created using the provided NMOS and PMOS from the standard library. The PMOS is connected to a nWell that is exported as vdd, and the NMOS is connected to a pWell exported as ground. The NMOS and PMOS are connected together according to the schematic. A screenshot of the layout is seen in Figure 5.
</p>

<p align="center">
  <img width="450" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/a2aeea65-f90a-4474-a80b-408748d38906">
</p>
<p align="center">
    Figure 4 (Layout of the NAND gate created in Electric VLSI)
</p>

<p>    
    The 3D view of the layout provides a clearer display of the components and how they are connected. 
</p>

<p align="center">
  <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0949042e-512e-43d3-a1d0-54e3db09f169">
</p>
<p align="center">
    Figure 5 (3D view of the layout created in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="nandSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The first simulation tests the switching point of the NAND gate. Ideally, the switching point of the inverter is half of vdd. The spice code puts 5V through one input and a pulse wave that goes from 0V to 5V, the transient is then recorded.
</p>
    
<p align="center">
  <img width="900" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d83f51a1-1d7f-4878-bfbd-1609a9c2e226">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the NAND gate switching point in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin in 0 pulse(0v 5v 10n 1n 1n 40n 40n)
        .tran 0 40n
<p align="center">
    Figure 7 (Spice simulation code for the NAND gate switching point)
</p>

<p>
    The results of the simulation were successful because the switching point was roughly half of vdd. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/356808d3-3c64-468b-b137-259d1590656b">
</p>
<p align="center">
    Figure 8 (Simulation results of the NAND gate switching point in LTSpice)
</p>

<p>
    The second simulation of the NAND gate tests the behavior of the logic values. The spice code applies 5V to vdd, a pulse wave to both inputs, and the timing of the waves is offset so that the various input combinations can be viewed in relation to the output. The transient is then recorded. 
</p>

<p align="center">
  <img width="1000" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/a43e18a9-ca9c-4f4c-b2f3-95f81afb08c1">
</p>
<p align="center">
    Figure 9 (Simulation schematic of the NAND gate logic values in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

    .include C5_models.txt
        
    vdd vdd 0 DC 5
    va va 0 pulse(0v 5v 0n 1n 1n 10n 20n)
    vb vb 0 pulse(0v 5v 5n 1n 1n 10n 20n)
    .trans 0 40n
<p align="center">
    Figure 10 (Spice simulation code for the NAND gate logic values)
</p>

<p>
    The results of the simulation show that the constructed NAND in VLSI is working as a conventional NAND gate. 
</p>

<p align="center">
  <img width="1500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/e25beb75-d462-4dc9-961a-cb8dbe4a37ca">
</p>
<p align="center">
    Figure 11 (Simulation results of the NAND gate logic values in LTSpice)
</p>
    
</dd></dl></dd></dl>

<h2> NOT </h2> <a name="not"></a>

<dl><dd><h3>Schematic</h3> <a name="notSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    A NOT gate was created in Electric VLSI. This will be used to construct the Full Adder in order to complete the lab. The schematic for the NOT gate can be seen in Figure 12.
</p>

<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/befcb96f-4a2d-494f-b5e2-77f299955ef8">
</p>
<p align="center">
    Figure 12 (Schematic of the Inverter 1 in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the inverter. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/e9539ba7-1199-45fe-b434-4537553142c2">
</p>
<p align="center">
    Figure 13 (Icon generated from the Inverter 1 schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="notLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The layout was created using the provided NMOS and PMOS from the standard library. The PMOS is connected to a nWell that is exported as vdd, and the NMOS is connected to a pWell exported as ground. The NMOS and PMOS are connected together according to the schematic. A screenshot of the layout is seen in Figure 14.
</p>

<p align="center">
  <img width="450" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/b044e900-ff8b-49ef-8fa9-a380712cd8f1">
</p>
<p align="center">
    Figure 14 (Layout of the NOT gate created in Electric VLSI)
</p>

<p>    
    The 3D view of the layout provides a clearer display of the components and how they are connected. 
</p>

<p align="center">
  <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/b47e18f4-7802-447d-86c7-224686b45456">
</p>
<p align="center">
    Figure 15 (3D view of the layout created in Electric VLSI)
</p>
    
</dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="notSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The simulation of the NOT gate tests the switching point of the logic gate. A pulse wave of 5v is applied to the input of the NOT gate. The transient is then recorded. 
</p>
    
<p align="center">
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/7c6ff54a-7e58-4c51-ba94-fdf1ce5e6e57">
</p>
<p align="center">
    Figure 16 (Simulation schematic of the NOT gate in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin d_in 0 pulse(0v 5v 10n 1n 1n 40n 40n)
        .tran 0 40n
<p align="center">
    Figure 17 (Spice simulation code for the inverter switching point)
</p>

<p>
    The results of the simulation were successful because the switching point was roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/986759aa-8381-4635-8cda-c278be0b17f0">
</p>
<p align="center">
    Figure 18 (Simulation results of the NOT gate switching point in LTSpice)
</p>

</dd></dl></dd></dl>

<h2> XOR </h2> <a name="xor"></a>

<dl><dd><h3>Schematic</h3> <a name="xorSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    An XOR gate was created in Electric VLSI. This will be used to construct the Full Adder in order to complete the lab. The schematic for the XOR gate can be seen in Figure 19.
</p>

<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/e17bcc01-4099-45cc-a087-7ed34e984dbb">
</p>
<p align="center">
    Figure 19 (Schematic of the XOR gate in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the XOR gate. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/276c2eaa-6769-4dc3-a00b-a05148fbc62d">
</p>
<p align="center">
    Figure 20 (Icon generated from the XOR gate schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="xorLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The layout was created using the provided NMOS and PMOS from the standard library. The PMOS transistors are connected to an nWell that is exported as vdd, and the NMOS transistors are connected to a pWell exported as ground. The NMOS and PMOS are connected together according to the schematic. A screenshot of the layout is seen in Figure 21.
</p>

<p align="center">
  <img width="450" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/7cfa0177-c678-4031-bc3c-9402ac3bf95b">
</p>
<p align="center">
    Figure 21 (Layout of the XOR gate created in Electric VLSI)
</p>

<p>    
    The 3D view of the layout provides a clearer display of the components and how they are connected. 
</p>

<p align="center">
  <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/87aa1787-1140-4094-9eaf-c711c8a7bc6b">
</p>
<p align="center">
    Figure 22 (3D view of the layout created in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="xorSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The first simulation of the XOR gate tests the switching point of the logic gate. Ideally, the switching point of the XOR gate is half of vdd. The spice code puts a constant 5V through one input, and a pulse wave of 5V through the other. The transient is then recorded. 
</p>
    
<p align="center">
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/41c0dd6a-baf2-4819-a8cc-ede1fc182388">
</p>
<p align="center">
    Figure 23 (Simulation schematic of the XOR gate in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin d_in 0 pulse(0v 5v 10n 1n 1n 40n 40n)
        .tran 0 40n
<p align="center">
    Figure 24 (Spice simulation code for the XOR gate switching point)
</p>

<p>
    The results of the simulation were successful because the switching point was roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/68bdaefd-9717-4015-9f08-0cd6eb04f311">
</p>
<p align="center">
    Figure 25 (Simulation results of the XOR gate switching point in LTSpice)
</p>

<p>
    The second simulation of the XOR gate tests the logic values. The spice code puts a pulse wave of 5V through both inputs, offset by 5ns. The transient is then recorded so that the output can be monitored based on different input combinations. 
</p>

<p align="center">
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/c0f7efdc-4b77-40b4-b6d3-929810523ca4">
</p>
<p align="center">
    Figure 26 (Simulation schematic of the XOR gate logic values in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        va va 0 pulse(0v 5v 0n 1n 1n 10n 20n)
        vb vb 0 pulse(0v 5v 5n 1n 1n 10n 20n)
        .tran 0 40n
<p align="center">
    Figure 27 (Spice simulation code for the XOR gate logic values)
</p>

<p>
    The results of the simulation were successful because the output shows a working XOR truth table. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/979dc294-0001-4abc-b393-69664a2873df">
</p>
<p align="center">
    Figure 28 (Simulation results of the XOR gate logic values in LTSpice)
</p>

</dd></dl></dd></dl>

<h2> Full Adder </h2> <a name="fulladder"></a>

<dl><dd><h3>Schematic</h3> <a name="fulladderSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The provided schematic consists of three NANDS and two XORS. To achieve the correct behavior of a full adder, the schematic was created using the previously created NAND and XOR schematics. The schematic can be seen in Figure 29. 
</p>

<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/37ff86fc-1aa0-411e-b58e-7656b94a550c">
</p>
<p align="center">
    Figure 29 (Schematic of the Full Adder in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the Full Adder. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/7dd58241-c9ec-4bd2-a01e-81332df425ec">
</p>
<p align="center">
    Figure 30 (Icon generated from the Full Adder schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="fulladderLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The layout was created using the previously created NAND and XOR layouts. The gate layouts are connected according to the Full Adder schematic. A screenshot of the layout is seen in Figure 31.
</p>

<p align="center">
  <img width="450" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/cbd331d6-ced5-45e7-98aa-488a1d54cfc1">
</p>
<p align="center">
    Figure 31 (Layout of the Full Adder created in Electric VLSI)
</p>

<p>    
    The 3D view of the layout provides a clearer display of the components and how they are connected. 
</p>

<p align="center">
  <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/9142827e-ef21-4a33-b1ed-9339505243a6">
</p>
<p align="center">
    Figure 32 (3D view of the layout created in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="fulladderSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The first simulation of the Full Adder tests the logic values of the schematic. The spice code puts a 5V pulse wave through each input. The pulse wave on B has an offset of 5ns, while the pulse wave on Cin has an offset of 2ns. The transient is then recorded. This allows the output to be monitored in comparison to various input combinations. 
</p>

<p align="center">
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/3c19fa82-238c-4bc8-bb44-5804335452a1">
</p>
<p align="center">
    Figure 33 (Simulation schematic of the Full Adder schematic logic values in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        va a 0 pulse(0v 5v 0n 1n 1n 10n 20n)
        vb b 0 pulse(0v 5v 5n 1n 1n 10n 20n)
        vcin cin 0 pulse(0v 5v 2n 1n 1n 10n 20n)
        .tran 0 60n
<p align="center">
    Figure 34 (Spice simulation code for the Full Adder schematic logic values)
</p>

<p>
    The results of the simulation were successful because the output of the schematic functioned as a conventional Full Adder. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/a09e5a1c-dc23-4567-a5a9-3c92d6bae55e">
</p>
<p align="center">
    Figure 35 (Simulation results of the Full Adder schematic logic values)
</p>

<p>
    The second simulation of the Full Adder tests the logic values of the layout. The spice code puts a 5V pulse wave through each input. The pulse wave on B has an offset of 5ns, while the pulse wave on Cin has an offset of 2ns. The transient is then recorded. This allows the output to be monitored in comparison to various input combinations. 
</p>

<p align="center">
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0c1a5793-9d12-4aea-bb0e-a4f5da5b8b4b">
</p>
<p align="center">
    Figure 36 (Simulation schematic of the Full Adder layout logic values in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation can be found in Figure 34
</p>

<p>
    The results of the simulation were successful because the output of the layout functioned as a conventional Full Adder. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/a3d94e3a-0674-4530-a8ef-9927285f379d">
</p>
<p align="center">
    Figure 37 (Simulation results of the Full Adder layout logic values in LTSpice)
</p>
    
</dd></dl></dd></dl>

<h2>Conclusion</h3>  <a name="conclusion"></a>

<p>
    Lab 5 explored the creation of a more complex CMOS circuit, the Full Adder. The Full Adder was created through various sub-components that were created as a part of the lab as well. The construction of the Full Adder gives insight into the design of complex CMOS circuits in VLSI. 
</p>

