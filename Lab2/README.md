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
<p align="center">Figure 1 (Provided schematic of the 5-bit R2R DAC)</p>
</dd><dl>

<h2>Pad Cell</h2> <a name="cell"></a>

<dl><dd><h3>Schematic</h3> <a name="cellSchem"></a></dd></dl> 

<dl><dd><dl><dd>
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

<dl><dd><h3>Layout</h3> <a name="cellLay"></a></dd></dl> 

<dl><dd><dl><dd><p>
    <p>    
        The layout was created using three n-well resistors each with a width of 15<span>&#411;</span> and length of 175.44<span>&#411;</span>. With the given value of R<sub>sq</sub> (855 <span>&#8486;</span>/square), and by choosing a width value, the length was calculated as follows:
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

<h2> Padframe </h2> <a name="padframe"></a>

<dl><dd><h3>Schematic</h3> <a name="padframeSchem"></a></dd></dl> 

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

<dl><dd><h3>Layout</h3> <a name="padframeLay"></a></dd></dl> 
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

<h2> Padframe DAC </h2> <a name="padDac"></a>

<dl><dd><h3>Schematic</h3> <a name="padDacSchem"></a></dd></dl> 

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

<dl><dd><h3>Layout</h3> <a name="padDacLay"></a></dd></dl> 
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


<h2>Conclusion</h3>  <a name="conclusion"></a>
Building out the voltage divider subcomponent for each input of the DAC improved the design efficiency immensely. Because the voltage divider was created and verified before implementing the 5-bit DAC, it brought some comfort to use the voltage divider in the design of the 5-bit DAC as well. The 5-bit R2R DAC created in this lab has been tested at each stage of development, and has passed all simulations. The 5-bit DAC library made in Electric VLSI can now be used for future projects and will also be used as a demonstration of how to connect pads to a circuit in Lab 2. 
</div>
