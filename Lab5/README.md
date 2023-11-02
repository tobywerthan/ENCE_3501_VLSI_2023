
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
   The purpose of this lab was to create a CMOS inverter with varying sizes in Electric VLSI. The inverters were constructed using NMOS, PMOS, NWell, and PWell components provided in the standard library. 
</p>

<p align="center">
  <img width="400" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/8de75467-340d-4dd3-829d-3e3eadee3387">
</p>
<p align="center">
    Figure 1 (Provided schematic of the Full Adde)
</p>
    
</dd><dl>

<h2> NAND </h2> <a name="nand"></a>

<dl><dd><h3>Schematic</h3> <a name="nandSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The provided schematic consists of an NMOS and a PMOS to form an inverter. To achieve the correct switching point, the PMOS is larger than the NMOS. For Inverter 1, the PMOS is 12 by 6 and the NMOS is 6 by 6 in drawn size. The schematic created in Electric VLSI reflects this in Figure 2. 
</p>

<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/f642b1fe-d95a-4673-abd2-294617d220da">
</p>
<p align="center">
    Figure 2 (Schematic of the NAND gate in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the inverter. 
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
    The first simulation of the NAND gate tests the switching point of the inverter. Ideally, the switching point of the inverter is half of vdd. The spice code puts 5V through the inverter over a period of 1 ms.
</p>
    
<p align="center">
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d83f51a1-1d7f-4878-bfbd-1609a9c2e226">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the NAND gate in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin in 0 pulse(0v 5v 10n 1n 1n 40n 40n)
        .tran 0 40n
<p align="center">
    Figure 7 (Spice simulation code for the NAND gate with no load)
</p>

<p>
    The results of the simulation were successful because the switching point was 2.416V. Because vdd was 5V, the switching point is roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/356808d3-3c64-468b-b137-259d1590656b">
</p>
<p align="center">
    Figure 8 (Simulation results of the NAND gate with no load in LTSpice)
</p>

<p>
    The second simulation of the NAND gate tests the behavior of the inverter with various load capacitor values. The spice code applies 5V to vdd, a pulse wave to vin, and analysis of the transient of the inverter with load values of 100f, 1p, 10p, and 100p. 
</p>

<p align="center">
  <img width="800" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/a43e18a9-ca9c-4f4c-b2f3-95f81afb08c1">
</p>
<p align="center">
    Figure 9 (Simulation schematic of the NAND gate with a load capacitor in Electric VLSI)
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
    Figure 10 (Spice simulation code for the NAND gate with a load capacitor)
</p>

<p>
    The results of the simulation show that the inverter's output is significantly affected by the load capacitors. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/e25beb75-d462-4dc9-961a-cb8dbe4a37ca">
</p>
<p align="center">
    Figure 11 (Simulation results of the NAND gate with the first load in LTSpice)
</p>
    
</dd></dl></dd></dl>

<h2> NOT </h2> <a name="not"></a>

<dl><dd><h3>Schematic</h3> <a name="notSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The provided schematic consists of an NMOS and a PMOS to form an inverter. To achieve the correct switching point, the PMOS is larger than the NMOS. For Inverter 1, the PMOS is 12 by 6 and the NMOS is 6 by 6 in drawn size. The schematic created in Electric VLSI reflects this in Figure 2. 
</p>

<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/befcb96f-4a2d-494f-b5e2-77f299955ef8">
</p>
<p align="center">
    Figure 2 (Schematic of the Inverter 1 in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the inverter. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/e9539ba7-1199-45fe-b434-4537553142c2">
</p>
<p align="center">
    Figure 3 (Icon generated from the Inverter 1 schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="notLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The layout was created using the provided NMOS and PMOS from the standard library. The PMOS is connected to a nWell that is exported as vdd, and the NMOS is connected to a pWell exported as ground. The NMOS and PMOS are connected together according to the schematic. A screenshot of the layout is seen in Figure 5.
</p>

<p align="center">
  <img width="450" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/b044e900-ff8b-49ef-8fa9-a380712cd8f1">
</p>
<p align="center">
    Figure 4 (Layout of Inverter 1 created in Electric VLSI)
</p>

<p>    
    The 3D view of the layout provides a clearer display of the components and how they are connected. 
</p>

<p align="center">
  <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/b47e18f4-7802-447d-86c7-224686b45456">
</p>
<p align="center">
    Figure 5 (3D view of the layout created in Electric VLSI)
</p>
    
</dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="notSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The first simulation of Inverter 1 tests the switching point of the inverter. Ideally, the switching point of the inverter is half of vdd. The spice code puts 5V through the inverter over a period of 1 ms.
</p>
    
<p align="center">
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/7c6ff54a-7e58-4c51-ba94-fdf1ce5e6e57">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the inverters in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin d_in 0 pulse(0v 5v 10n 1n 1n 40n 40n)
        .tran 0 40n
<p align="center">
    Figure 7 (Spice simulation code for the inverters with no load)
</p>

<p>
    The results of the simulation were successful because the switching point was 2.416V. Because vdd was 5V, the switching point is roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/986759aa-8381-4635-8cda-c278be0b17f0">
</p>
<p align="center">
    Figure 8 (Simulation results of Inverter 1 with no load in LTSpice)
</p>

</dd></dl></dd></dl>

<h2> XOR </h2> <a name="xor"></a>

<dl><dd><h3>Schematic</h3> <a name="xorSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The provided schematic consists of an NMOS and a PMOS to form an inverter. To achieve the correct switching point, the PMOS is larger than the NMOS. For Inverter 1, the PMOS is 12 by 6 and the NMOS is 6 by 6 in drawn size. The schematic created in Electric VLSI reflects this in Figure 2. 
</p>

<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/e17bcc01-4099-45cc-a087-7ed34e984dbb">
</p>
<p align="center">
    Figure 2 (Schematic of the Inverter 1 in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the inverter. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/276c2eaa-6769-4dc3-a00b-a05148fbc62d">
</p>
<p align="center">
    Figure 3 (Icon generated from the Inverter 1 schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="xorLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The layout was created using the provided NMOS and PMOS from the standard library. The PMOS is connected to a nWell that is exported as vdd, and the NMOS is connected to a pWell exported as ground. The NMOS and PMOS are connected together according to the schematic. A screenshot of the layout is seen in Figure 5.
</p>

<p align="center">
  <img width="450" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/7cfa0177-c678-4031-bc3c-9402ac3bf95b">
</p>
<p align="center">
    Figure 4 (Layout of Inverter 1 created in Electric VLSI)
</p>

<p>    
    The 3D view of the layout provides a clearer display of the components and how they are connected. 
</p>

<p align="center">
  <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/87aa1787-1140-4094-9eaf-c711c8a7bc6b">
</p>
<p align="center">
    Figure 5 (3D view of the layout created in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="xorSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The first simulation of Inverter 1 tests the switching point of the inverter. Ideally, the switching point of the inverter is half of vdd. The spice code puts 5V through the inverter over a period of 1 ms.
</p>
    
<p align="center">
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/41c0dd6a-baf2-4819-a8cc-ede1fc182388">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the inverters in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin d_in 0 pulse(0v 5v 10n 1n 1n 40n 40n)
        .tran 0 40n
<p align="center">
    Figure 7 (Spice simulation code for the inverters with no load)
</p>

<p>
    The results of the simulation were successful because the switching point was 2.416V. Because vdd was 5V, the switching point is roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/68bdaefd-9717-4015-9f08-0cd6eb04f311">
</p>
<p align="center">
    Figure 8 (Simulation results of Inverter 1 with no load in LTSpice)
</p>

<p>
    The second simulation of Inverter 1 tests the switching point of the inverter. Ideally, the switching point of the inverter is half of vdd. The spice code puts 5V through the inverter over a period of 1 ms.
</p>

<p align="center">
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/c0f7efdc-4b77-40b4-b6d3-929810523ca4">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the inverters in Electric VLSI)
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
    Figure 7 (Spice simulation code for the inverters with no load)
</p>

<p>
    The results of the simulation were successful because the switching point was 2.416V. Because vdd was 5V, the switching point is roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/979dc294-0001-4abc-b393-69664a2873df">
</p>
<p align="center">
    Figure 8 (Simulation results of Inverter 1 with no load in LTSpice)
</p>

</dd></dl></dd></dl>

<h2> Full Adder </h2> <a name="fulladder"></a>

<dl><dd><h3>Schematic</h3> <a name="fulladderSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The provided schematic consists of an NMOS and a PMOS to form an inverter. To achieve the correct switching point, the PMOS is larger than the NMOS. For Inverter 1, the PMOS is 12 by 6 and the NMOS is 6 by 6 in drawn size. The schematic created in Electric VLSI reflects this in Figure 2. 
</p>

<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/37ff86fc-1aa0-411e-b58e-7656b94a550c">
</p>
<p align="center">
    Figure 2 (Schematic of the Inverter 1 in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the inverter. 
</p>
![FullAdder_icon_1](https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/7dd58241-c9ec-4bd2-a01e-81332df425ec)

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/7dd58241-c9ec-4bd2-a01e-81332df425ec">
</p>
<p align="center">
    Figure 3 (Icon generated from the Inverter 1 schematic in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="fulladderLay"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>    
    The layout was created using the provided NMOS and PMOS from the standard library. The PMOS is connected to a nWell that is exported as vdd, and the NMOS is connected to a pWell exported as ground. The NMOS and PMOS are connected together according to the schematic. A screenshot of the layout is seen in Figure 5.
</p>

<p align="center">
  <img width="450" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/cbd331d6-ced5-45e7-98aa-488a1d54cfc1">
</p>
<p align="center">
    Figure 4 (Layout of Inverter 1 created in Electric VLSI)
</p>

<p>    
    The 3D view of the layout provides a clearer display of the components and how they are connected. 
</p>

<p align="center">
  <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/9142827e-ef21-4a33-b1ed-9339505243a6">
</p>
<p align="center">
    Figure 5 (3D view of the layout created in Electric VLSI)
</p>

</dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="fulladderSim"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>
    The first simulation of Inverter 1 tests the switching point of the inverter. Ideally, the switching point of the inverter is half of vdd. The spice code puts 5V through the inverter over a period of 1 ms.
</p>

<p align="center">
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/3c19fa82-238c-4bc8-bb44-5804335452a1">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the inverters in Electric VLSI)
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
    Figure 7 (Spice simulation code for the inverters with no load)
</p>

<p>
    The results of the simulation were successful because the switching point was 2.416V. Because vdd was 5V, the switching point is roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/a09e5a1c-dc23-4567-a5a9-3c92d6bae55e">
</p>
<p align="center">
    Figure 8 (Simulation results of Inverter 1 with no load in LTSpice)
</p>

<p>
    The second simulation of Inverter 1 tests the switching point of the inverter. Ideally, the switching point of the inverter is half of vdd. The spice code puts 5V through the inverter over a period of 1 ms.
</p>

<p align="center">
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0c1a5793-9d12-4aea-bb0e-a4f5da5b8b4b">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the inverters in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation can be found in Figure .........
</p>

<p>
    The results of the simulation were successful because the switching point was 2.416V. Because vdd was 5V, the switching point is roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/a3d94e3a-0674-4530-a8ef-9927285f379d">
</p>
<p align="center">
    Figure 8 (Simulation results of Inverter 1 with no load in LTSpice)
</p>
    
</dd></dl></dd></dl>

<h2>Conclusion</h3>  <a name="conclusion"></a>

<p>
    Lab 4 explored the creation of a logic gate using CMOS technology. The inverter was created in varying sizes and was tested with multiple load capacitor values. This inverter will  be used to create more complex CMOS layouts in the future. The figure below is a 3D rendering of both inverters. Inverter 2 is on the left and Inverter1 is on the right. 
</p>

<p align="center">
    <img width="900" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/6c66c6d2-0051-4cd8-b6a5-610a51c69717">
</p>
<p align="center">
    Figure 22 (3D Rendering of both inverters in Fusion360)
</p>


