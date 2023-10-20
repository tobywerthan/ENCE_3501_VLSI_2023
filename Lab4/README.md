# Lab 4: CMOS Inverter In Electric VLSI

Toby Werthan

10/20/2023

ENCE 3501

## Table of Contents
1. [Introduction](#introduction)
2. [Inverter 1](#vdiv)
    1. [Schematic](#vdivSchem)
    2. [Layout](#vdivLay)
    3. [Simulations](#vdivSim)
3. [Inverter 2](#dac)
    1. [Schematic](#dacSchem)
    2. [Layout](#dacLay)
    3. [Simulations](#dacSim)
4. [Conclusion](#conclusion)

*Note: If images are hard to view, please click on them. A new tab will open, displaying the full-size image.*
<div align="left">
<h2>Introduction</h2>  <a name="introduction"></a>
<dl><dd>
    <p>
       The purpose of this lab was to create a CMOS inverter with varying sizes in Electric VLSI. The inverters were constructed using NMOS, PMOS, NWell, and PWell components provided in the standard library. 
    </p>
    <p align="center">
  <img width="400" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/8de75467-340d-4dd3-829d-3e3eadee3387">
</p>
<p align="center">Figure 1 (Provided schematic of the inverter)</p>
</dd><dl>

<h2> Inverter 1 </h2> <a name="vdiv"></a>

<dl><dd><h3>Schematic</h3> <a name="vdivSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    <p>    
        The provided schematic consists of an NMOS and a PMOS to form an inverter. To achieve the correct switching point, the PMOS is larger than the NMOS. For Inverter 1, the PMOS is 12 by 6 and the NMOS is 6 by 6 in drawn size. The schematic created in Electric VLSI reflects this in Figure 2. 
    </p>
<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/15c6e131-2acd-4d6e-b568-6fa15b7ca730">
</p>
<p align="center">Figure 2 (Schematic of the Inverter 1 in Electric VLSI)</p>
    <p>    
        An icon was then generated from the schematic. This is an important step as the icon will be used to simulate the inverter. 
    </p>
<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/eeff7ef8-5b0f-42ef-9822-0e5845e25dbb">
</p>
<p align="center">Figure 3 (Icon generated from the Inverter 1 schematic in Electric VLSI)</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="vdivLay"></a></dd></dl> 

<dl><dd><dl><dd><p>
    <p>    
        The layout was created using the provided NMOS and PMOS from the standard library. The PMOS is connected to a nWell that is exported as vdd, and the NMOS is connected to a pWell exported as ground. The NMOS and PMOS are connected together according to the schematic. A screenshot of the layout is seen in Figure 5.
    </p>
    <p align="center">
      <img width="450" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/29169f0d-77a3-40f0-806b-a7a4459a0dde">
    </p>
    <p align="center">Figure 4 (Layout of Inverter 1 created in Electric VLSI)</p>
    <p>    
        The 3D view of the layout provides a clearer display of the components and how they are connected. 
    </p>
    <p align="center">
      <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0f4c45eb-c75c-4d2e-9b78-ee179dc978d6">
    </p>
    <p align="center">Figure 5 (3D view of the layout created in Electric VLSI)</p>
    
</p></dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="vdivSim"></a></dd></dl> 
<dl><dd><dl><dd>
    <p>
        The first simulation of Inverter 1 tests the switching point of the inverter. Ideally, the switching point of the inverter is half of vdd. The spice code puts 5V through the inverter over a period of 1 ms.
    </p>
        <p align="center">
      <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/ba260e1e-8eba-4a66-bf4a-e54b7854f9cd">
    </p>
    <p align="center">Figure 6 (Simulation schematic of the inverters in Electric VLSI)</p>
    <p>
    A snippet of the spice code for the simulation is provided below:
    </p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin vin 0 DC 0
        .dc vin 0 5 1m
<p align="center">Figure 7 (Spice simulation code for the inverters with no load)</p>
    <p>
        The results of the simulation were successful because the switching point was 2.416V. Because vdd was 5V, the switching point is roughly half of vdd. 
    </p>
    </p>
        <p align="center">
      <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d81979c2-36e0-489b-8668-6e5c13fd1bd1">
    </p>
    <p align="center">Figure 8 (Simulation results of Inverter 1 with no load in LTSpice)</p>

<p>
    The second simulation of Inverter 1 tests the behavior of the inverter with various load capacitor values. The spice code applies 5V to vdd, a pulse wave to vin, and analysis of the transient of the inverter with load values of 100f, 1p, 10p, and 100p. 
</p>
    <p align="center">
      <img width="800" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0a697f6e-72c2-495b-81ba-d377fafc5f78">
    </p>
    <p align="center">Figure 9 (Simulation schematic of the inverters with a load capacitor in Electric VLSI)</p>
    <p>
    A snippet of the spice code for the simulation is provided below:
    </p>

    .include C5_models.txt
        
    vdd vdd 0 DC 5
    vin vin 0 pulse(0v 5v 5n 1n 1n 12n 25n)
    .step param x list 100f 1p 10p 100p
    .trans 0 25n 0 100p
<p align="center">Figure 10 (Spice simulation code for the inverters with a load capacitor)</p>
    <p>
        The results of the simulation show that the inverter's output is significantly affected by the load capacitors. 
    </p>
    </p>
        <p align="center">
      <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0bc38806-7cb9-413a-ba2d-6d5d5f7c4509">
    </p>
    <p align="center">Figure 11 (Simulation results of Inverter 1 with the first load in LTSpice)</p>
<p>
    The third simulation of Inverter 1 tests the behavior of the inverter with various load capacitor values. The spice code applies 5V to vdd, a pulse wave to vin, and analysis of the transient of the inverter with load values of 1f, 10f, and 100f. 
</p>
        <p align="center">
      <img width="800" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/5e6d8aa0-132b-4066-ab82-ef03dc11e712">
        </p>
    <p align="center">Figure 12 (Second simulation schematic of the inverters with a load capacitor in Electric VLSI)</p>
    <p>
    A snippet of the spice code for the simulation is provided below:
    </p>

    .include C5_models.txt
        
    vdd vdd 0 DC 5
    vin vin 0 pulse(0v 5v 5n 1n 1n 12n 25n)
    .step param x list 1f 10f 100f
    .trans 0 25n 0 100p
<p align="center">Figure 13 (Second spice simulation code for the inverters with a load capacitor)</p>
    <p>
        The results of the simulation show that as the load capacitor value decreases, the inverter begins to behave as expected. 
    </p>
    </p>
        <p align="center">
      <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/2ba49a83-4753-4dcb-8fb7-860d08d995a8">
    </p>
    <p align="center">Figure 14 (Simulation results of Inverter 2 with the second load in LTSpice)</p>

</dd></dl></dd></dl>

<h2> Inverter 2 </h2> <a name="dac"></a>

<dl><dd><h3>Schematic</h3> <a name="dacSchem"></a></dd></dl> 

<dl><dd><dl><dd>
<p>
    Inverter 2 has the same schematic as Inverter 1. The only difference between the two is the dimensions of the CMOS components. The PMOS in this schematic has a drawn width of 48 with the same length of 6. The NMOS now has a drawn width of 24 with the same length of 6. 
</p>
<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/03663347-6e1b-49c9-9645-9fb1681c311d">
</p>
<p align="center">Figure 15 (Schematic of Inverter 2 in Electric VLSI)</p>
    <p>An icon was then generated from the schematic. This is an important step as the icon will be used in the simulation for the inverters</p>
<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/822cc06d-ff25-4d32-84d9-4f6e5878cc08">
</p>
<p align="center">Figure 16 (Icon of Inverter 2 in Electric VLSI)</p>
    
</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="dacLay"></a></dd></dl> 
<dl><dd><dl><dd>
    <p>
        The layout for this larger inverter was created by cascading four Inverter 1 layouts. This creates a larger inverter by only increasing the width of the CMOS components. 
    </p>
    <p align="center">
      <img width="800" height="450" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/e7b4bd79-9dc3-473d-b020-58b0f952d39b">
    </p>
<p align="center">Figure 17 (Layout of Inverter 2 in Electric VLSI)</p>
    <p>The 3D view of the layout provides a clearer display of the MOSFETS and how they are connected.</p>
        <p align="center">
      <img width="600" height="450" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/77e3163f-9b81-4f36-8c9c-17119f2e6951">
    </p>
<p align="center">Figure 18 (3D View of the layout in Electric VLSI)</p>
</dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="dacSim"></a></dd></dl> 

<dl><dd><dl><dd>
    <p>
        The first simulation of Inverter 2 tests the switching point of the inverter. Ideally, the switching point of the inverter is half of vdd. The schematic for the simulation can be seen in Figure 6. The spice code puts 5V through the inverter over a period of 1 ms. The spice code can be found in Figure 7. 
    </p>
    <p>
        The results of the simulation were successful because the output voltage was 2.25V. We can start to see the effects of increasing the size of the gate. As the CMOS size increases, the impedance does as well. 
    </p>
    </p>
        <p align="center">
      <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/4b69ab81-a5d9-4ffc-9319-b872e162725b">
    </p>
    <p align="center">Figure 19 (Simulation results of Inverter 2 with no load in LTSpice)</p>
<p>
    The second simulation of Inverter 2 tests the behavior of the inverter with various load capacitor values. The schematic for the simulation can be seen in Figure 9. The spice code applies 5V to vdd, a pulse wave to vin, and analysis of the transient of the inverter with load values of 100f, 1p, 10p, and 100p. The spice code can be found in Figure 10. 
</p>
    <p>
        The results of the simulation are similar to the results of Inverter 1, the load capacitor has a large effect on the output voltage. 
    </p>
    </p>
        <p align="center">
      <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/81fd017a-1916-4aa3-affb-7ea00d74cb3f">
    </p>
    <p align="center">Figure 20 (Simulation results of Inverter 2 with the first load in LTSpice)</p>
<p>
    The third simulation of Inverter 2 tests the behavior of the inverter with various load capacitor values. The schematic for the simulation can be seen in Figure 12. The spice code applies 5V to vdd, a pulse wave to vin, and analysis of the transient of the inverter with load values of 1f, 10f, and 100f. The spice code can be found in Figure 13. 
</p>
    <p>
        The results of the simulation show that as the load capacitor decreases, the inverter begins to behave as expected. 
    </p>
    </p>
        <p align="center">
      <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/288139fd-0c8a-4da2-a55a-4445e16ddeaf">
    </p>
    <p align="center">Figure 21 (Simulation results of Inverter 2 with the second load in LTSpice)</p>

</dd></dl></dd></dl>

<h2>Conclusion</h3>  <a name="conclusion"></a>
<p>
    Lab 4 explored the creation of a logic gate using CMOS technology. The inverter was created in varying sizes and was tested with multiple load capacitor values. This inverter will  be used to create more complex CMOS layouts in the future. The figure below is a 3D rendering of both inverters. Inverter 2 is on the left and Inverter1 is on the right. 
</p>
    <p align="center">
  <img width="900" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/6c66c6d2-0051-4cd8-b6a5-610a51c69717">
</p>
<p align="center">Figure 22 (3D Rendering of both inverters in Fusion360)</p>
</div>

