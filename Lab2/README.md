# Lab 2: Padframe DAC In Electric VLSI

Toby Werthan

10/6/2023

ENCE 3501

## Table of Contents
1. [Introduction](#introduction)
2. [Pad Cell](#cell)
    1. [Schematic](#cellSchem)
    2. [Layout](#cellLay)
3. [Padframe](#padframe)
    1. [Schematic](#padframeSchem)
    2. [Layout](#padframeLay)
4. [Padframe DAC](#padDac)
    1. [Schematic](#padDacSchem)
    2. [Layout](#padDacLay)
5. [Conclusion](#conclusion)

*Note: If images are hard to view, please click on them. A new tab will open, displaying the full-size image.*
<div align="left">
<h2>Introduction</h2>  <a name="introduction"></a>
<dl><dd>
    <p>
       The purpose of this lab was to create a 5-bit R2R DAC in Electric VLSI. The DAC was created through voltage divider subcomponents, this helped streamline the design process. The schematic that the VLSI designs presented in this document are based on can be found in Figure 1. 
    </p>
    <p align="center">
  <img width="500" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/4ef6dbc3-81e1-406c-afe3-d20e2f3b2006">
</p>
<p align="center">Figure 1 (Schematic of a pad frame with the connected 5-bit DAC)</p>
</dd><dl>

<h2>Pad Cell</h2> <a name="cell"></a>

<dl><dd><h3>Schematic</h3> <a name="cellSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    <p>    
        When designing the schematic in Electric VLSI, the resistor connected to the input was implemented as two 10k<span>&#8486;</span> resistors in series. All of the inputs and outputs were created through exports. 
    </p>
<p align="center">
  <img width="460" height="350" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/7cab1a99-886e-456a-9899-b8375553fd3c">
</p>
<p align="center">Figure 2 (Schematic of the pad cell in Electric VLSI)</p>
    <p>    
        An icon was then generated from the schematic. This is an important step as the icon will be used to quickly build the 5-bit DAC. 
    </p>
<p align="center">
  <img width="400" height="100" src=https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/1c41cc2f-fc2f-4762-a57f-5918cf334449">
</p>
<p align="center">Figure 3 (Icon generated from the pad cell in Electric VLSI)</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="cellLay"></a></dd></dl> 

<dl><dd><dl><dd><p>
    <p>    
        The layout was created using three n-well resistors each with a width of 15<span>&#411;</span> and length of 175.44<span>&#411;</span>. With the given value of R<sub>sq</sub> (855 <span>&#8486;</span>/square), and by choosing a width value, the length was calculated as follows:
    </p>
    
<p align="center">
  <img width="400" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/a8e95bc4-af4b-464e-ace6-ae18f1acd124">
</p>
<p align="center">Figure 4 (Layout of the pad cell created in Electric VLSI)</p>

<p>    
    The 3D view of the layout provides a clearer display of the n-well resistors and how they are connected. 
</p>
<p align="center">
  <img width="500" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/57658f7d-5351-4500-9335-afa907c40512">
</p>
<p align="center">Figure 5 (3D view of the layout created in Electric VLSI)</p>

</p></dd></dl></dd></dl>

<h2> Padframe </h2> <a name="padframe"></a>

<dl><dd><h3>Schematic</h3> <a name="padframeSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>Five of the previously created voltage divider icons were used to construct a 5-bit R2R DAC schematic. An additional 10k<span>&#8486;</span> resistor was connected to the first voltage divider of the DAC and ground.</p>
<p align="center">
  <img width="400" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d81aef2e-1134-47df-b781-2ae18ee316ff">
</p>
<p align="center">Figure 6 (Schematic of the padframe in Electric VLSI)</p>
    <p>An icon was then generated from the schematic. This is an important step as the icon will be used in the simulation schematic for the 5-bit R2R DAC.</p>
<p align="center">
  <img width="300" height="200" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/acd1a8aa-63a1-47c5-a0eb-2cde9f6927a7">
</p>
<p align="center">Figure 7 (Icon of the padframe schematic in Electric VLSI)</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="padframeLay"></a></dd></dl> 
<dl><dd><dl><dd>
    <p>The 5-bit R2R DAC layout was created using five of the previously created voltage divider layouts. The inputs and outputs are connected to their respective nodes using metal contacts. </p>
    <p align="center">
      <img width="450" height="450" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/2826707a-618b-4dba-a9af-1e09bba1ea02">
    </p>
<p align="center">Figure 8 (Layout of the padframe in Electric VLSI)</p>
    <p>The 3D view of the layout provides a clearer display of the previous layouts and how they are connected.</p>
        <p align="center">
      <img width="600" height="450" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/4f414315-234f-4d28-8ef9-3e3603187b1a">
    </p>
<p align="center">Figure 9 (3D view of the layout in Electric VLSI)</p>
</dd></dl></dd></dl>

<h2> Padframe DAC </h2> <a name="padDac"></a>

<dl><dd><h3>Schematic</h3> <a name="padDacSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>Five of the previously created voltage divider icons were used to construct a 5-bit R2R DAC schematic. An additional 10k<span>&#8486;</span> resistor was connected to the first voltage divider of the DAC and ground.</p>
<p align="center">
  <img width="600" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/97c34dca-2a00-4242-9e53-2f373ca5e7da">
</p>
<p align="center">Figure 10 (Schematic of the padframe with the 5-bit DAC connected in Electric VLSI)</p>
    <p>An icon was then generated from the schematic. This is an important step as the icon will be used in the simulation schematic for the 5-bit R2R DAC.</p>
<p align="center">
  <img width="250" height="300" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/072b4fa0-36d0-4683-8a1f-9d64bd503e0c">
</p>
<p align="center">Figure 11 (Icon of the padframe with the 5-bit DAC connected in Electric VLSI)</p>
    
</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="padDacLay"></a></dd></dl> 
<dl><dd><dl><dd>
    <p>The 5-bit R2R DAC layout was created using five of the previously created voltage divider layouts. The inputs and outputs are connected to their respective nodes using metal contacts. </p>
    <p align="center">
      <img width="500" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/10450cc7-0708-4429-a77b-2fbb7cdcecc9">
    </p>
<p align="center">Figure 12 (Layout of the padframe with the 5-bit DAC connected in Electric VLSI)</p>
    <p>The 3D view of the layout provides a clearer display of the previous layouts and how they are connected.</p>
        <p align="center">
      <img width="600" height="450" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/6e38fb20-90dd-46b1-815e-2c35455feb25">
    </p>
<p align="center">Figure 13 (3D view of the layout in Electric VLSI)</p>
        <p>The 3D view of the layout provides a clearer display of the previous layouts and how they are connected.</p>
        <p align="center">
      <img width="900" height="675" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/7a52d5ba-61e0-4e35-8fd9-2893b187b400">
    </p>
<p align="center">Figure 14 (3D render of the layout in Electric VLSI)</p>
</dd></dl></dd></dl>

<h2>Conclusion</h3>  <a name="conclusion"></a>
Building out the voltage divider subcomponent for each input of the DAC improved the design efficiency immensely. Because the voltage divider was created and verified before implementing the 5-bit DAC, it brought some comfort to use the voltage divider in the design of the 5-bit DAC as well. The 5-bit R2R DAC created in this lab has been tested at each stage of development, and has passed all simulations. The 5-bit DAC library made in Electric VLSI can now be used for future projects and will also be used as a demonstration of how to connect pads to a circuit in Lab 2. 
</div>
