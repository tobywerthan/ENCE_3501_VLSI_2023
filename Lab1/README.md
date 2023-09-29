# Lab 1

Toby Werthan

09/29/2023

ENCE 3501

## Table of Contents
1. [Introduction](#introduction)
2. [Voltage Divider](#vdiv)
    1. [Schematic](#vdivSchem)
    2. [Layout](#vdivLay)
    3. [Simulations](#vdivSim)
3. [5-Bit R2R DAC](#dac)
    1. [Hand Calculations](#dacHand)
    2. [Schematic](#dacSchem)
    3. [Layout](#dacLay)
    4. [Simulations](#dacSim)
4. [Conclusion](#conclusion)
<div align="left">
<h2>Introduction</h2>  <a name="introduction"></a>
<dl><dd>
    <p>
       The purpose of this lab was to create a 5-bit R2R DAC in Electric VLSI. The DAC was created through voltage divider subcomponents, which helped streamline the design process. The schematic that the VLSI designs presented in this document are based on can be found in Figure 1. 
    </p>
    <p align="center">
  <img width="460" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/c8f5528c-e35c-443d-ae9e-9c57a5af6a0e">
</p>
<p align="center">Figure 1 (Provided schematic of the 5-bit R2R DAC)</p>
</dd><dl>

<h2> Voltage Divider </h2> <a name="vdiv"></a>

<dl><dd><h3>Schematic</h3> <a name="vdivSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    <p>    
        The schematic provided consisted of two resistors. The resistor connected to the input has double the resistance of the resistor connected to ground. The resistor connected to ground has a resistance value of 10k<span>&#8486;</span>, meaning the resistor connected to the input has a resistance of 20k<span>&#8486;</span>. 
    </p>
<p align="center">
  <img width="300" height="300" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d8a0ed93-952e-4907-bcc3-6ae84d8f48ec">
</p>
<p align="center">Figure 2 (Schematic provided for the voltage divider)</p>
    <p>    
        When designing the schematic in Electric VLSI, the resistor connected to the input was implemented as two 10k<span>&#8486;</span> resistors in series. All of the inputs and outputs were created through exports. 
    </p>
<p align="center">
  <img width="460" height="300" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/586d0a62-8ba9-4b1d-8890-c4dbf2423686">
</p>
<p align="center">Figure 3 (Schematic of the voltage divider in Electric VLSI)</p>
    <p>    
        An icon was then generated from the schematic. This is an important step as the icon will be used to quickly build the 5-bit DAC. 
    </p>
<p align="center">
  <img width="270" height="300" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/3cf9f3d1-42e4-42c7-857a-abcbea9a2550">
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
  <img width="850" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/bfc9021e-8cd8-4161-981f-2da6ebe5809e">
</p>
<p align="center">Figure 5 (Layout of the voltage divider created in Electric VLSI)</p>

<p>    
    The 3D view of the layout provides a clearer display of the n-well resistors and how they are connected. 
</p>
<p align="center">
  <img width="750" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/76a24d5d-e9b1-4ea4-9890-029b8a843473">
</p>
<p align="center">Figure 6 (3D view of the layout created in Electric VLSI)</p>

</p></dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="vdivSim"></a></dd></dl> 
<dl><dd><dl><dd>
<p>
The simulation of the schematic passed 5V through the input of the circuit. A successful simulation is determined by the voltage value of the output, which would ideally be 1.667V. The icon generated from the original schematic was used in this simulation, which implemented the circuit as a "black box".
</p>
    <p align="center">
  <img width="300" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d89cf0c0-1a84-491f-a73e-bec12c26fac1">
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
  <img width="400" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/e751828d-8389-4b5f-a963-e4d57679cda9">
</p>
<p align="center">Figure 9 (Simulation schematic results in LTSpice)</p>
<p>
The simulation of the layout passed 5V through the input of the circuit. A successful simulation is determined by the voltage value of the output, which would ideally be 1.667V. The original layout was used in this simulation, which implemented the circuit as a "black box".
</p>
    <p align="center">
  <img width="700" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/bb68848b-8ac1-4f55-9d2e-dcc2654c203a">
</p>
<p align="center">Figure 10 (Simulation layout of the voltage divider in Electric VLSI)</p>
<p>
<p>
A snippet of the spice code can be found in Figure 8.
</p>
<p>
    The results of the simulation were successful because the output voltage was 1.667V. This means that the layout was accurately designed. 
</p>
</p>
    <p align="center">
  <img width="400" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/59f78a15-7d4f-4c71-aca1-120cdab89d24">
</p>
<p align="center">Figure 11 (Simulation layout results in LTSpice)</p>

<p>
    An NCC check is run after the completion of the layout to ensure that the schematic and layout have the same topologies. The results of the NCC check on the voltage divider can be found in Figure 9. 
</p>
</p>
    <p align="center">
  <img width="1000" height="100" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/fb66ce67-9c2d-402d-bc9c-52ce8b17aa99">
</p>
<p align="center">Figure 12 (NCC check results of the voltage divider)</p>

</dd></dl></dd></dl>

<h2> 5-Bit R2R DAC </h2> <a name="dac"></a>

<dl><dd><h3>Hand Calculations</h3> <a name="dacHand"></a></dd></dl> 

<dl><dd><dl><dd> 
    
<p>To find the equivalent resistance of the 5-bit DAC, all inputs must be grounded. The resistance should be measured between the output and ground. The hand calculations for R<sub>EQ</sub> can be seen in Figure 13.</p>
<p align="center">
  <img width="600" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0aac0efc-ed6e-47cb-bafb-3074b97c7455">
</p>
<p align="center">Figure 13 (Hand calculations for R<sub>EQ</sub> of the DAC)</p>   

<p>All of the information is needed to calculate the delay caused by a 10pF load capacitor on the 5-bit DAC. In order to calculate the delay, the equation <span>&#964;</span> = C*R<sub>EQ</sub> is used. The hand calculations for the delay can be found in Figure 14.</p>
<p align="center">
  <img width="600" height="300" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d9f7e3c5-e883-45d1-bc4f-ebe7723a6a46">
</p>
<p align="center">Figure 14 (Hand calculations for the delay caused by a 10pF load capacitor)</p>   


</dd></dl></dd></dl>

<dl><dd><h3>Schematic</h3> <a name="dacSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>Five of the previously created voltage divider icons were used to construct a 5-bit R2R DAC schematic. An additional 10k<span>&#8486;</span> resistor was connected to the first voltage divider of the DAC and ground.</p>
<p align="center">
  <img width="400" height="800" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/e84802ee-b4ac-4806-a32a-16dc44e80916">
</p>
<p align="center">Figure 15 (Schematic of the 5-bit R2R DAC in Electric VLSI)</p>
    <p>An icon was then generated from the schematic. This is an important step as the icon will be used in the simulation schematic for the 5-bit R2R DAC.</p>
<p align="center">
  <img width="300" height="250" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/730415a0-79d7-4fd2-a2bc-a9bacfdd393e">
</p>
<p align="center">Figure 16 (Icon of the 5-bit R2R DAC schematic in Electric VLSI)</p>
    
</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="dacLay"></a></dd></dl> 
<dl><dd><dl><dd>
    <p>The 5-bit R2R DAC layout was created using five of the previously created voltage divider layouts. The inputs and outputs are connected to their respective nodes using metal contacts. </p>
    <p align="center">
      <img width="450" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/36f439e1-52d5-454e-903f-bfd98acce083">
    </p>
<p align="center">Figure 17 (Layout of the 5-bit R2R DAC in Electric VLSI)</p>
    <p>The 3D view of the layout provides a clearer display of the previous layouts and how they are connected.</p>
        <p align="center">
      <img width="600" height="450" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d0a0f24b-673e-415c-b44c-4ffeb0203924">
    </p>
<p align="center">Figure 18 (3D View of the layout in Electric VLSI)</p>
</dd></dl></dd></dl>

<dl><dd><h3>Simulations</h3> <a name="dacSim"></a></dd></dl> 

<dl><dd><dl><dd>
    <p>
The simulation of the schematic passed 5V through the inputs b0 and b1, while all other inputs were grounded. A successful simulation is determined by the voltage value of the output, which would ideally be 0.46875V. The icon generated from the schematic was used in this simulation, which implemented the circuit as a "black box".
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

<p>
The schematic was simulated with b4 connected to a pulse source, and the rest of the inputs connected to ground. A 10pF load driving capacitor was connected to the circuit as well. A successful simulation depends on the delay of the DAC with the 10pF capacitor, which ideally would be around 100ns. 
</p>
<p align="center">
  <img width="600" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/a9e0a431-74d0-423e-a9be-5da4597f274a">
</p>
<p align="center">Figure 22 (Simulation load capacitor schematic of the 5-bit R2R DAC)</p>
    
<p>
A snippet of the spice code for the simulation is provided below:
</p>
    
    vin vin 0 pulse(0v 2v 1u 1f 1f 3u 6u)
    .tran 0 2.4u 0 100p
<p align="center">Figure 23 (Spice simulation code for the load capacitor 5-bit R2R DAC)</p>
<p>
    The results of the simulation were successful because the measured delay of the DAC with the 10pF load capacitor was 70.83ns. This means that the layout was accurately designed. 
</p>
</p>
    <p align="center">
  <img width="700" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/6a48b06f-bd67-40b4-95cf-17547dbc0384">
</p>
<p align="center">Figure 24 (Simulation load capacitor schematic results in LTSpice)</p>

The simulation of the layout passed 5V through the inputs b0 and b1, while all other inputs were grounded. A successful simulation is determined by the voltage value of the output, which would ideally be 0.46875V. The previously created 5-bit DAC was used in this simulation, which implemented entire layout as a "black box".
</p>
    <p align="center">
  <img width="500" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/03aa4a4a-d1e7-41ae-a7ab-95c6e9001ef7">
</p>
<p align="center">Figure 25 (Simulation layout of the 5-bit R2R DAC in Electric VLSI)</p>

<p>
A snippet of the spice code can be found below:
</p>

    v4 b4 0
    v3 b3 0
    v2 b2 0
    v1 b1 b0
    vin b0 0 DC 5
    .op
<p align="center">Figure 26 (Spice simulation code for the layout of the 5-bit R2R DAC)</p>   
<p>
    The results of the simulation were successful because the output voltage was 0.46875V. This means that the layout was accurately designed. 
</p>
</p>
    <p align="center">
  <img width="400" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/72494f77-87fc-4932-90c7-f83f5f6ea5d0">
</p>
<p align="center">Figure 27 (Simulation layout results in LTSpice)</p>

<p>
    An NCC check is run after the completion of the layout to ensure that the schematic and layout have the same topologies. The results of the NCC check on the 5-bt DAC can be found in Figure 28. 
</p>
</p>
    <p align="center">
  <img width="1000" height="100" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/8538a7fb-fcc1-427c-a585-887e7f7bdad5">
</p>
<p align="center">Figure 28 (NCC check results of the 5-bit DAC)</p>
</dd></dl></dd></dl>

<h3>Conclusion</h3>  <a name="conclusion"></a>
Building out the voltage divider subcomponent for each input of the DAC improved the design efficiency immensely. Because the voltage divider was created and verified before implementing the 5-bit DAC, it brought some comfort to use the voltage divider in the design of the 5-bit DAC as well. The 5-bit R2R DAC created in this lab has been tested at each stage of development, and has passed all simulations. The 5-bit DAC library made in Electric VLSI can now be used for future projects and will also be used as a demonstration of how to connect pads to a circuit in Lab 2. 
</div>
