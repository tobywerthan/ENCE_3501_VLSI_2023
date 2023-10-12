# Lab 3: Integrated NMOS Circuit with Electrostatic Discharge Protection

Toby Werthan

10/13/2023

ENCE 3501

## Table of Contents
1. [Introduction](#introduction)
2. [Pad Cell with ESD](#cell)
    1. [Schematic](#cellSchem)
    2. [Layout](#cellLay)
3. [Padframe with ESD](#padframe)
    1. [Schematic](#padframeSchem)
    2. [Layout](#padframeLay)
4. [Final IC with ESD](#padDac)
    1. [Schematic](#padDacSchem)
    2. [Layout](#padDacLay)
5. [Conclusion](#conclusion)

*Note: If images are hard to view, please click on them. A new tab will open, displaying the full-size image.*
<div align="left">
<h2>Introduction</h2>  <a name="introduction"></a>
<dl><dd>
    <p>
       The purpose of this lab was to create a padframe and connect it to the 5-bit DAC created in lab 1. The padframe was created through pad cell subcomponents and buses for exports. The schematic that the VLSI designs presented in this document are based on can be found in Figure 1. 
    </p>
    <p align="center">
      <img width="450" height="375" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/349415f8-8b4b-43d3-9a58-0478429615aa">
    </p>
<p align="center">Figure 1 (Schematic of a pad frame with the connected 5-bit DAC)</p>
</dd><dl>

<h2>Pad Cell with ESD</h2> <a name="cell"></a>

<dl><dd><h3>Schematic</h3> <a name="cellSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    <p>    
        The design for the pad cell schematic was simple. The pad cell is simply a connection for the inner circuit. The layout is the more complex part of this process. 
    </p>
<p align="center">
  <img width="250" height="625" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/4a4f7a4e-b07e-4624-a412-bc7572ad5d1b">
<p align="center">Figure 2 (Schematic of the pad cell with ESD protection in Electric VLSI)</p>
    <p>    
        An icon was then generated from the schematic. This is an important step as the icon will be used to quickly build the 5-bit DAC. 
    </p>
<p align="center">
  <img width="450" height="375" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/4a4f7a4e-b07e-4624-a412-bc7572ad5d1b">
</p>
<p align="center">Figure 3 (Icon generated from the pad cell with ESD protection in Electric VLSI)</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="cellLay"></a></dd></dl> 

<dl><dd><dl><dd><p>
    <p>    
        The layout for the pad cell was created with three layers. The first layer was metal one, which lies at the bottom of the pad. The second layer is metal two and is connected to metal 1 through a series of vias. The last layer is the overglass layer which lies on top of metal two. The overglass helps connect the pad to external pins. 
    </p>
    
<p align="center">
  <img width="325" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0ae45432-c1fe-41d4-857e-ba36e2a3f9ca">
</p>
<p align="center">Figure 4 (Layout of the pad cell with ESD protection created in Electric VLSI)</p>

<p>    
    The 3D view of the layout provides a clearer display of the layers and how they are oriented. The overglass is rendered as if it is hovering over the metal two layer. This is not the case, this is just a graphical feature. 
</p>
<p align="center">
  <img width="550" height="425" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/927dae64-75cc-4bad-95e0-b55140a4432d">
</p>
<p align="center">Figure 5 (3D view of the layout created in Electric VLSI)</p>

</p></dd></dl></dd></dl>

<h2> Padframe with ESD </h2> <a name="padframe"></a>

<dl><dd><h3>Schematic</h3> <a name="padframeSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>The padframe schematic was created using the pad icon. The icon is connected to a bus with eight exports named, pin[1] through pin[8]. Eight pins are required in this design as the 5-bit DAC will have five outputs and inputs. </p>
<p align="center">
  <img width="425" height="350" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/ea17ac8b-08bb-4846-9671-cea8d7d0b554">
</p>
<p align="center">Figure 6 (Schematic of the padframe with ESD protection in Electric VLSI)</p>
    <p>An icon was then generated from the schematic. This is an important step as the icon will be used to connect the 5-bit DAC.</p>
<p align="center">
  <img width="400" height="300" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/87b0d755-d2ec-4b8b-bea6-51426861b3dd">
</p>
<p align="center">Figure 7 (Icon of the padframe with ESD protection schematic in Electric VLSI)</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="padframeLay"></a></dd></dl> 
<dl><dd><dl><dd>
    <p>The padframe layout was created by generating an array of eight-by-eight pads. The pads in the center were deleted, along with the pads on the corners.</p>
    <p align="center">
      <img width="450" height="450" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d5ce5da1-6509-495e-a536-4567785f2e9d">
    </p>
<p align="center">Figure 8 (Layout of the padframe with ESD protection in Electric VLSI)</p>
    <p>The 3D view of the layout provides a clearer display of how the pads are oriented</p>
    <p align="center">
      <img width="600" height="475" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/470f6254-ab52-48a9-a701-a74437986093">
    </p>
<p align="center">Figure 9 (3D view of the layout in Electric VLSI)</p>
</dd></dl></dd></dl>

<h2> Final IC with ESD </h2> <a name="padDac"></a>

<dl><dd><h3>Schematic</h3> <a name="padDacSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>The schematic of the padframe connected to the 5-bit DAC was created by connecting a bus of eight pins to the padframe icon. Each pin was then individually connected to the 5-bit DAC.</p>
<p align="center">
  <img width="700" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/fc638277-2d97-4faf-a7c9-06f640015134">
</p>
<p align="center">Figure 10 (Schematic of the padframe with ESD protection connected to an NMOS transistor)</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="padDacLay"></a></dd></dl> 
<dl><dd><dl><dd>
    <p>The 5-bit DAC was connected to each respective pin using a metal one-to-metal two contacts. The transition between these two metal layers is essential as the pads would not be properly connected otherwise.</p>
    <p align="center">
      <img width="550" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/9694a9c1-8f6d-4be5-8713-05e7446aa646">
    </p>
<p align="center">Figure 11 (Layout of the padframe with ESD protection connected to an NMOS transistor)</p>
    <p>The 3D view of the layout provides a clearer display of the padframe, ESD protection and it connects to the NMOS transistor.</p>
    <p align="center">
      <img width="600" height="450" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/c3a72abc-c0c8-4104-b0b7-bbd2280c0eb0">
    </p>
<p align="center">Figure 12 (3D view of the layout in Electric VLSI)</p>
    <p>A final 3D render of the NMOS connected to the padframe shows a realistic image of what the IC might look like.</p>
    <p align="center">
      <img width="863.5" height="432.5" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/afc1f3e9-8846-4228-a9bc-073c0e64db1b">
    </p>
<p align="center">Figure 13 (3D render of the layout in Fusion360)</p>
</dd></dl></dd></dl>

<h2>Conclusion</h3>  <a name="conclusion"></a>
    Connecting the 5-bit DAC to the padframe brought the find 5-bit DAC IC one step closer to completion. The pads can now be connected to the outside world, meaning the DAC could theoretically be connected and used for a more complex circuit. This configuration does not provide any ESD protection, the DAC can be easily damaged if no safeguards are implemented. Lab 3 explores securing the connections between the DAC and pads from getting damaged by ESD.
</div>
