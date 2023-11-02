
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

<p align="center" width="1000">
    
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
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/15c6e131-2acd-4d6e-b568-6fa15b7ca730">
</p>
<p align="center">
    Figure 2 (Schematic of the NAND gate in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the inverter. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/eeff7ef8-5b0f-42ef-9822-0e5845e25dbb">
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
  <img width="450" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/29169f0d-77a3-40f0-806b-a7a4459a0dde">
</p>
<p align="center">
    Figure 4 (Layout of the NAND gate created in Electric VLSI)
</p>

<p>    
    The 3D view of the layout provides a clearer display of the components and how they are connected. 
</p>

<p align="center">
  <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0f4c45eb-c75c-4d2e-9b78-ee179dc978d6">
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
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/ba260e1e-8eba-4a66-bf4a-e54b7854f9cd">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the NAND gate in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin vin 0 DC 0
        .dc vin 0 5 1m
<p align="center">
    Figure 7 (Spice simulation code for the NAND gate with no load)
</p>

<p>
    The results of the simulation were successful because the switching point was 2.416V. Because vdd was 5V, the switching point is roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d81979c2-36e0-489b-8668-6e5c13fd1bd1">
</p>
<p align="center">
    Figure 8 (Simulation results of the NAND gate with no load in LTSpice)
</p>

<p>
    The second simulation of the NAND gate tests the behavior of the inverter with various load capacitor values. The spice code applies 5V to vdd, a pulse wave to vin, and analysis of the transient of the inverter with load values of 100f, 1p, 10p, and 100p. 
</p>

<p align="center">
  <img width="800" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0a697f6e-72c2-495b-81ba-d377fafc5f78">
</p>
<p align="center">
    Figure 9 (Simulation schematic of the NAND gate with a load capacitor in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

    .include C5_models.txt
        
    vdd vdd 0 DC 5
    vin vin 0 pulse(0v 5v 5n 1n 1n 12n 25n)
    .step param x list 100f 1p 10p 100p
    .trans 0 25n 0 100p
<p align="center">
    Figure 10 (Spice simulation code for the NAND gate with a load capacitor)
</p>

<p>
    The results of the simulation show that the inverter's output is significantly affected by the load capacitors. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0bc38806-7cb9-413a-ba2d-6d5d5f7c4509">
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
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/15c6e131-2acd-4d6e-b568-6fa15b7ca730">
</p>
<p align="center">
    Figure 2 (Schematic of the Inverter 1 in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the inverter. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/eeff7ef8-5b0f-42ef-9822-0e5845e25dbb">
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
  <img width="450" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/29169f0d-77a3-40f0-806b-a7a4459a0dde">
</p>
<p align="center">
    Figure 4 (Layout of Inverter 1 created in Electric VLSI)
</p>

<p>    
    The 3D view of the layout provides a clearer display of the components and how they are connected. 
</p>

<p align="center">
  <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0f4c45eb-c75c-4d2e-9b78-ee179dc978d6">
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
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/ba260e1e-8eba-4a66-bf4a-e54b7854f9cd">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the inverters in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin vin 0 DC 0
        .dc vin 0 5 1m
<p align="center">
    Figure 7 (Spice simulation code for the inverters with no load)
</p>

<p>
    The results of the simulation were successful because the switching point was 2.416V. Because vdd was 5V, the switching point is roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d81979c2-36e0-489b-8668-6e5c13fd1bd1">
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
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/15c6e131-2acd-4d6e-b568-6fa15b7ca730">
</p>
<p align="center">
    Figure 2 (Schematic of the Inverter 1 in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the inverter. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/eeff7ef8-5b0f-42ef-9822-0e5845e25dbb">
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
  <img width="450" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/29169f0d-77a3-40f0-806b-a7a4459a0dde">
</p>
<p align="center">
    Figure 4 (Layout of Inverter 1 created in Electric VLSI)
</p>

<p>    
    The 3D view of the layout provides a clearer display of the components and how they are connected. 
</p>

<p align="center">
  <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0f4c45eb-c75c-4d2e-9b78-ee179dc978d6">
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
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/ba260e1e-8eba-4a66-bf4a-e54b7854f9cd">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the inverters in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin vin 0 DC 0
        .dc vin 0 5 1m
<p align="center">
    Figure 7 (Spice simulation code for the inverters with no load)
</p>

<p>
    The results of the simulation were successful because the switching point was 2.416V. Because vdd was 5V, the switching point is roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d81979c2-36e0-489b-8668-6e5c13fd1bd1">
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
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/15c6e131-2acd-4d6e-b568-6fa15b7ca730">
</p>
<p align="center">
    Figure 2 (Schematic of the Inverter 1 in Electric VLSI)
</p>

<p>    
    An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the inverter. 
</p>

<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/eeff7ef8-5b0f-42ef-9822-0e5845e25dbb">
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
  <img width="450" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/29169f0d-77a3-40f0-806b-a7a4459a0dde">
</p>
<p align="center">
    Figure 4 (Layout of Inverter 1 created in Electric VLSI)
</p>

<p>    
    The 3D view of the layout provides a clearer display of the components and how they are connected. 
</p>

<p align="center">
  <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0f4c45eb-c75c-4d2e-9b78-ee179dc978d6">
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
  <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/ba260e1e-8eba-4a66-bf4a-e54b7854f9cd">
</p>
<p align="center">
    Figure 6 (Simulation schematic of the inverters in Electric VLSI)
</p>

<p>
    A snippet of the spice code for the simulation is provided below:
</p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin vin 0 DC 0
        .dc vin 0 5 1m
<p align="center">
    Figure 7 (Spice simulation code for the inverters with no load)
</p>

<p>
    The results of the simulation were successful because the switching point was 2.416V. Because vdd was 5V, the switching point is roughly half of vdd. 
</p>

<p align="center">
  <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d81979c2-36e0-489b-8668-6e5c13fd1bd1">
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

</p>

