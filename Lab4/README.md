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
  <img width="350" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/8de75467-340d-4dd3-829d-3e3eadee3387">
</p>
<p align="center">Figure 1 (Provided schematic of the inverter)</p>
</dd><dl>

<h2> Inverter 1 </h2> <a name="vdiv"></a>

<dl><dd><h3>Schematic</h3> <a name="vdivSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    <p>    
        The schematic provided consisted of two resistors. The resistor connected to the input has double the resistance of the resistor connected to ground. The resistor connected to ground has a resistance value of 10k<span>&#8486;</span>, meaning the resistor connected to the input has a resistance of 20k<span>&#8486;</span>. 
    </p>
<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/15c6e131-2acd-4d6e-b568-6fa15b7ca730">
</p>

<p align="center">Figure 2 (Schematic of the Inverter 1 in Electric VLSI)</p>
    <p>    
        An icon was then generated from the schematic. This is an important step as the icon will be used to quickly build the 5-bit DAC. 
    </p>
<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/eeff7ef8-5b0f-42ef-9822-0e5845e25dbb">
</p>
<p align="center">Figure 4 (Icon generated from the Inverter 1 schematic in Electric VLSI)</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="vdivLay"></a></dd></dl> 

<dl><dd><dl><dd><p>
    <p>    
        The layout was created using three n-well resistors each with a width of 15<span>&#411;</span> and length of 175.44<span>&#411;</span>. With the given value of R<sub>sq</sub> (855 <span>&#8486;</span>/square), and by choosing a width value, the length was calculated as follows:
    </p>
    <p align="center">
      <img width="450" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/29169f0d-77a3-40f0-806b-a7a4459a0dde">
    </p>
    <p align="center">Figure 5 (Layout of Inverter 1 created in Electric VLSI)</p>
    <p>    
        The 3D view of the layout provides a clearer display of the MOSFETS and how they are connected. 
    </p>
    <p align="center">
      <img width="700" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0f4c45eb-c75c-4d2e-9b78-ee179dc978d6">
    </p>
    <p align="center">Figure 6 (3D view of the layout created in Electric VLSI)</p>
    
</p></dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="vdivSim"></a></dd></dl> 
<dl><dd><dl><dd>
    <p>
        Inverter 1 no load 
    </p>
        <p align="center">
      <img width="800" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/ba260e1e-8eba-4a66-bf4a-e54b7854f9cd">
    </p>
    <p align="center">Figure 7 (Simulation schematic of the inverters in Electric VLSI)</p>
    <p>
    A snippet of the spice code for the simulation is provided below:
    </p>

        .include C5_models.txt
        
        vdd vdd 0 DC 5
        vin vin 0 DC 0
        .dc vin 0 5 1m
<p align="center">Figure 8 (Spice simulation code for the inverters with no load)</p>
    <p>
        The results of the simulation were successful because the output voltage was 1.667V. This means that the schematic was accurately designed. 
    </p>
    </p>
        <p align="center">
      <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d81979c2-36e0-489b-8668-6e5c13fd1bd1">
    </p>
    <p align="center">Figure 9 (Simulation results of Inverter 1 with no load in LTSpice)</p>

<p>
    Inverter 1 load 1
</p>
    <p align="center">
      <img width="800" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0a697f6e-72c2-495b-81ba-d377fafc5f78">
    </p>
    <p align="center">Figure 7 (Simulation schematic of the inverters with a load capacitor in Electric VLSI)</p>
    <p>
    A snippet of the spice code for the simulation is provided below:
    </p>

    .include C5_models.txt
        
    vdd vdd 0 DC 5
    vin vin 0 pulse(0v 5v 5n 1n 1n 12n 25n)
    .step param x list 100f 1p 10p 100p
    .trans 0 25n 0 100p
<p align="center">Figure 8 (Spice simulation code for the inverters with a load capacitor)</p>
    <p>
        The results of the simulation were successful because the output voltage was 1.667V. This means that the schematic was accurately designed. 
    </p>
    </p>
        <p align="center">
      <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0bc38806-7cb9-413a-ba2d-6d5d5f7c4509">
    </p>
    <p align="center">Figure 9 (Simulation results of Inverter 1 with the first load in LTSpice)</p>
<p>
    Inverter 1 load 2
</p>
        <p align="center">
      <img width="800" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/5e6d8aa0-132b-4066-ab82-ef03dc11e712">
        </p>
    <p align="center">Figure 7 (Second simulation schematic of the inverters with a load capacitor in Electric VLSI)</p>
    <p>
    A snippet of the spice code for the simulation is provided below:
    </p>

    .include C5_models.txt
        
    vdd vdd 0 DC 5
    vin vin 0 pulse(0v 5v 5n 1n 1n 12n 25n)
    .step param x list 1f 10f 100f
    .trans 0 25n 0 100p
<p align="center">Figure 8 (Second spice simulation code for the inverters with a load capacitor)</p>
    <p>
        The results of the simulation were successful because the output voltage was 1.667V. This means that the schematic was accurately designed. 
    </p>
    </p>
        <p align="center">
      <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/2ba49a83-4753-4dcb-8fb7-860d08d995a8">
    </p>
    <p align="center">Figure 9 (Simulation results of Inverter 2 with the second load in LTSpice)</p>

</dd></dl></dd></dl>

<h2> Inverter 2 </h2> <a name="dac"></a>

<dl><dd><h3>Schematic</h3> <a name="dacSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>Five of the previously created voltage divider icons were used to construct a 5-bit R2R DAC schematic. An additional 10k<span>&#8486;</span> resistor was connected to the first voltage divider of the DAC and ground.</p>
<p align="center">
  <img width="525" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/03663347-6e1b-49c9-9645-9fb1681c311d">
</p>
<p align="center">Figure 15 (Schematic of Inverter 2 in Electric VLSI)</p>
    <p>An icon was then generated from the schematic. This is an important step as the icon will be used in the simulation schematic for the 5-bit R2R DAC.</p>
<p align="center">
  <img width="500" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/822cc06d-ff25-4d32-84d9-4f6e5878cc08">
</p>
<p align="center">Figure 16 (Icon of Inverter 2 in Electric VLSI)</p>
    
</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="dacLay"></a></dd></dl> 
<dl><dd><dl><dd>
    <p>The 5-bit R2R DAC layout was created using five of the previously created voltage divider layouts. The inputs and outputs are connected to their respective nodes using metal contacts. </p>
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
        Inverter 2 no load 
    </p>
    <p>
        The results of the simulation were successful because the output voltage was 1.667V. This means that the schematic was accurately designed. 
    </p>
    </p>
        <p align="center">
      <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/4b69ab81-a5d9-4ffc-9319-b872e162725b">
    </p>
    <p align="center">Figure 9 (Simulation results of Inverter 2 with no load in LTSpice)</p>

<p>
    Inverter 2 load 1
</p>
    <p>
        The results of the simulation were successful because the output voltage was 1.667V. This means that the schematic was accurately designed. 
    </p>
    </p>
        <p align="center">
      <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/81fd017a-1916-4aa3-affb-7ea00d74cb3f">
    </p>
    <p align="center">Figure 9 (Simulation results of Inverter 2 with the first load in LTSpice)</p>
<p>
    Inverter 2 load 2
</p>
    <p>
        The results of the simulation were successful because the output voltage was 1.667V. This means that the schematic was accurately designed. 
    </p>
    </p>
        <p align="center">
      <img width="1000" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/288139fd-0c8a-4da2-a55a-4445e16ddeaf">
    </p>
    <p align="center">Figure 9 (Simulation results of Inverter 2 with the second load in LTSpice)</p>

</dd></dl></dd></dl>

<h2>Conclusion</h3>  <a name="conclusion"></a>
Building out the voltage divider subcomponent for each input of the DAC improved the design efficiency immensely. Because the voltage divider was created and verified before implementing the 5-bit DAC, it brought some comfort to use the voltage divider in the design of the 5-bit DAC as well. The 5-bit R2R DAC created in this lab has been tested at each stage of development, and has passed all simulations. The 5-bit DAC library made in Electric VLSI can now be used for future projects and will also be used as a demonstration of how to connect pads to a circuit in Lab 2. 

</p>
    <p align="center">
  <img width="900" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/6c66c6d2-0051-4cd8-b6a5-610a51c69717">
</p>
<p align="center">Figure 21 (3D Rendering of both inverters in Fusion360)</p>
</div>

