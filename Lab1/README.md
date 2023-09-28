# Lab 1
## Table of Contents
1. [Introduction](#introduction)
2. [Voltage Divider](#vdiv)
    1. [Schematic](#vdivSchem)
    2. [Layout](#vdivLay)
    3. [Simulations](#vdivSim)
3. [5-Bit R2R DAC](#dac)
    1. [Schematic](#dacSchem)
    2. [Layout](#dacLay)
    3. [Simulations](#dacSim)
4. [Conclusion](#conclusion)
## Introduction <a name="introduction"></a>
<dl>
    <dd>hello</dd>
<dl>

<h2> Voltage Divider </h2> <a name="vdiv"></a>

<dl><dd><h3>Schematic</h3> <a name="vdivSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    <p>    
        The schematic provided consisted of two resistors. The resistor connected to the input has double the resistance of the resistor connected to ground. The resisor connected to ground has a resistance value of 10k<span>&#8486;</span>, meaning the resistor connected to the input has a resistance of 20k<span>&#8486;</span>. 
    </p>
<p align="center">
  <img width="300" height="300" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d8a0ed93-952e-4907-bcc3-6ae84d8f48ec">
</p>
<p align="center">Figure 1 (Schematic provided for the voltage divider)</p>
    <p>    
        When designing the schematic in Electric VLSI, the resistor connected to the input was implemented as two 10k<span>&#8486;</span> resistors in series. All of the inputs and outputs were created through exports. 
    </p>
<p align="center">
  <img width="460" height="300" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/586d0a62-8ba9-4b1d-8890-c4dbf2423686">
</p>
<p align="center">Figure 2 (Schematic of the voltage divider in Electric VLSI)</p>
    <p>    
        An icon was then generated from the schematic. This is an important step as the icon will be used to quickly build the 5-bit DAC. 
    </p>
<p align="center">
  <img width="270" height="300" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/3cf9f3d1-42e4-42c7-857a-abcbea9a2550">
</p>
<p align="center">Figure 3 (Icon generated from the voltage divider in Electric VLSI)</p>

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
<p align="center">Figure 4 (Layout of the voltage divider created in Electric VLSI)</p>

<p>    
    The 3D view of the layout provides a clearer display of the n-well resistors and how they are connected. 
</p>
<p align="center">
  <img width="750" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/76a24d5d-e9b1-4ea4-9890-029b8a843473">
</p>
<p align="center">Figure 5 (3D view of the layout created in Electric VLSI)</p>

</p></dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="vdivSim"></a></dd></dl> 
<dl><dd><dl><dd>
<p>
The simulation of the schematic passed 5V through the input of the circuit. A successful simulation is determined by the voltage value of the output, which would ideally be 1.667V. 
</p>
</dd></dl></dd></dl>

<h2> 5-Bit R2R DAC </h2> <a name="dac"></a>

<dl><dd><h3>Schematic</h3> <a name="dacSchem"></a></dd></dl> 
<dl><dd><dl><dd><p>Hello World</p></dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="dacLay"></a></dd></dl> 
<dl><dd><dl><dd><p>Hello World</p></dd></dl></dd></dl>

<dl><dd><h3>Simulation</h3> <a name="dacSim"></a></dd></dl> 
<dl><dd><dl><dd><p>Hello World</p></dd></dl></dd></dl>

<h3>Conclusion</h3>  <a name="conclusion"></a>
hello
