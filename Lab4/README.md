# Lab 1: 5-Bit R2R DAC In Electric VLSI

Toby Werthan

09/29/2023

ENCE 3501

## Table of Contents
1. [Introduction](#introduction)
2. [Inverter 1](#vdiv)
    1. [Schematic](#vdivSchem)
    2. [Layout](#vdivLay)
    3. [Simulations](#vdivSim)
3. [Inverter 2](#dac)
    2. [Schematic](#dacSchem)
    3. [Layout](#dacLay)
    4. [Simulations](#dacSim)
4. [Conclusion](#conclusion)

*Note: If images are hard to view, please click on them. A new tab will open, displaying the full-size image.*
<div align="left">
<h2>Introduction</h2>  <a name="introduction"></a>
<dl><dd>
    <p>
       The purpose of this lab was to create a 5-bit R2R DAC in Electric VLSI. The DAC was created through voltage divider subcomponents, this helped streamline the design process. The schematic that the VLSI designs presented in this document are based on can be found in Figure 1. 
    </p>
    <p align="center">
  <img width="460" height="500" src="">
</p>
<p align="center">Figure 1 (Provided schematic of the 5-bit R2R DAC)</p>
</dd><dl>

<h2> Inverter 1 </h2> <a name="vdiv"></a>

<dl><dd><h3>Schematic</h3> <a name="vdivSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    <p>    
        The schematic provided consisted of two resistors. The resistor connected to the input has double the resistance of the resistor connected to ground. The resistor connected to ground has a resistance value of 10k<span>&#8486;</span>, meaning the resistor connected to the input has a resistance of 20k<span>&#8486;</span>. 
    </p>
<p align="center">
  <img width="300" height="300" src="">
</p>
<p align="center">Figure 2 (Schematic provided for the voltage divider)</p>
    <p>    
        When designing the schematic in Electric VLSI, the resistor connected to the input was implemented as two 10k<span>&#8486;</span> resistors in series. All of the inputs and outputs were created through exports. 
    </p>
<p align="center">
  <img width="460" height="300" src="">
</p>
<p align="center">Figure 3 (Schematic of the voltage divider in Electric VLSI)</p>
    <p>    
        An icon was then generated from the schematic. This is an important step as the icon will be used to quickly build the 5-bit DAC. 
    </p>
<p align="center">
  <img width="270" height="300" src="">
</p>
<p align="center">Figure 4 (Icon generated from the voltage divider in Electric VLSI)</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="vdivLay"></a></dd></dl> 

<dl><dd><dl><dd><p>
    <p>    
        The layout was created using three n-well resistors each with a width of 15<span>&#411;</span> and length of 175.44<span>&#411;</span>. With the given value of R<sub>sq</sub> (855 <span>&#8486;</span>/square), and by choosing a width value, the length was calculated as follows:
    </p>
    
        10000 = (855)*(L/15)
        L = (10000*15)/855
        L = 175.44
            
<p>    
    The inputs and outputs are connected to their respective nodes using metal contacts. 
</p>
<p align="center">
  <img width="850" height="400" src="">
</p>
<p align="center">Figure 5 (Layout of the voltage divider created in Electric VLSI)</p>

<p>    
    The 3D view of the layout provides a clearer display of the n-well resistors and how they are connected. 
</p>
<p align="center">
  <img width="750" height="400" src="">
</p>
<p align="center">Figure 6 (3D view of the layout created in Electric VLSI)</p>

</p></dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="vdivSim"></a></dd></dl> 
<dl><dd><dl><dd>
<p>
The simulation of the schematic passed 5V through the input of the circuit. A successful simulation is determined by the voltage value of the output, which would ideally be 1.667V. The icon generated from the original schematic was used in this simulation, this implemented the circuit as a "black box".
</p>
    <p align="center">
  <img width="300" height="400" src="">
</p>
<p align="center">Figure 7 (Simulation schematic of the voltage divider in Electric VLSI)</p>
<p>
A snippet of the spice code for the simulation is provided below:
</p>
    
    vdd vin 0 DC 5V
    .op
<p align="center">Figure 8 (Spice simulation code for the voltage divider)</p>

<p>
    The results of the simulation were successful because the output voltage was 1.667V. This means that the schematic was accurately designed. 
</p>
</p>
    <p align="center">
  <img width="400" height="400" src="">
</p>
<p align="center">Figure 9 (Simulation schematic results in LTSpice)</p>

</dd></dl></dd></dl>

<h2> Inverter 2 </h2> <a name="dac"></a>

<dl><dd><h3>Schematic</h3> <a name="dacSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>Five of the previously created voltage divider icons were used to construct a 5-bit R2R DAC schematic. An additional 10k<span>&#8486;</span> resistor was connected to the first voltage divider of the DAC and ground.</p>
<p align="center">
  <img width="400" height="800" src="">
</p>
<p align="center">Figure 15 (Schematic of the 5-bit R2R DAC in Electric VLSI)</p>
    <p>An icon was then generated from the schematic. This is an important step as the icon will be used in the simulation schematic for the 5-bit R2R DAC.</p>
<p align="center">
  <img width="300" height="250" src="">
</p>
<p align="center">Figure 16 (Icon of the 5-bit R2R DAC schematic in Electric VLSI)</p>
    
</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="dacLay"></a></dd></dl> 
<dl><dd><dl><dd>
    <p>The 5-bit R2R DAC layout was created using five of the previously created voltage divider layouts. The inputs and outputs are connected to their respective nodes using metal contacts. </p>
    <p align="center">
      <img width="450" height="600" src="">
    </p>
<p align="center">Figure 17 (Layout of the 5-bit R2R DAC in Electric VLSI)</p>
    <p>The 3D view of the layout provides a clearer display of the previous layouts and how they are connected.</p>
        <p align="center">
      <img width="600" height="450" src="">
    </p>
<p align="center">Figure 18 (3D View of the layout in Electric VLSI)</p>
</dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="dacSim"></a></dd></dl> 

<dl><dd><dl><dd>
    <p>
The simulation of the schematic passed 5V through the inputs b0 and b1, while all other inputs were grounded. A successful simulation is determined by the voltage value of the output, which would ideally be 0.46875V. The icon generated from the schematic was used in this simulation, this implemented the circuit as a "black box".
</p>
    <p align="center">
  <img width="500" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/8052a52f-7bd4-4fcb-8a73-a16e50ea678f">
</p>
<p align="center">Figure 19 (Simulation schematic of the 5-bit R2R DAC in Electric VLSI)</p>
<p>
A snippet of the spice code for the simulation is provided below:
</p>
    
    vin vin 0 DC 5
    .op
<p align="center">Figure 20 (Spice simulation code for the 5-bit R2R DAC)</p>

<p>
    The results of the simulation were successful because the output voltage was 0.46875V. This means that the schematic was accurately designed. 
</p>
</p>
    <p align="center">
  <img width="400" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/8de6f3b8-c6b1-463a-8048-1c157a6301cb">
</p>
<p align="center">Figure 21 (Simulation schematic results in LTSpice)</p>

</dd></dl></dd></dl>

<h2>Conclusion</h3>  <a name="conclusion"></a>
Building out the voltage divider subcomponent for each input of the DAC improved the design efficiency immensely. Because the voltage divider was created and verified before implementing the 5-bit DAC, it brought some comfort to use the voltage divider in the design of the 5-bit DAC as well. The 5-bit R2R DAC created in this lab has been tested at each stage of development, and has passed all simulations. The 5-bit DAC library made in Electric VLSI can now be used for future projects and will also be used as a demonstration of how to connect pads to a circuit in Lab 2. 

</p>
    <p align="center">
  <img width="400" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/8de6f3b8-c6b1-463a-8048-1c157a6301cb">
</p>
<p align="center">Figure 21 (Simulation schematic results in LTSpice)</p>
</div>

