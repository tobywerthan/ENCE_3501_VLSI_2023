# Lab 3: Integrated NMOS Circuit with Electrostatic Discharge Protection

Toby Werthan

10/13/2023

ENCE 3501

## Table of Contents
1. [Introduction](#introduction)
2. [Pad Cell with ESD Protection](#cell)
    1. [Schematic](#cellSchem)
    2. [Layout](#cellLay)
3. [Padframe with ESD Protection](#padframe)
    1. [Schematic](#padframeSchem)
    2. [Layout](#padframeLay)
4. [Final IC with ESD Protection](#padDac)
    1. [Schematic](#padDacSchem)
    2. [Layout](#padDacLay)
5. [Conclusion](#conclusion)

*Note: If images are hard to view, please click on them. A new tab will open, displaying the full-size image.*
<div align="left">
<h2>Introduction</h2>  <a name="introduction"></a>
<dl><dd>
    <p>
       The purpose of this lab was to incorporate the simple electrostatic discharge protection circuit seen in Figure 1 with the padframe constructed in Lab 2. The circuit consists of two diodes that regulate the voltage through the output node. Integrating ESD protection in the padframe will help prevent the internal logic from being damaged. The final integrated circuit consists of a pad cell that has ESD protection, a padframe consisting of pad cells with ESD protection, and finally an NMOS transistor connected to the ESD-protected padframe. 
    </p>
    <p align="center">
      <img width="250" height="600" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/349415f8-8b4b-43d3-9a58-0478429615aa">
    </p>
<p align="center">Figure 1 (Schematic of a simple electrostatic discharge protection circuit)</p>
</dd><dl>

<h2>Pad Cell with ESD Protection</h2> <a name="cell"></a>

<dl><dd><h3>Schematic</h3> <a name="cellSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    <p>    
        The schematic for the pad cell with ESD protection (Figure 2) is similar to Figure 1. The voltage source is connected to a pActive-nWell diode, while ground is connected to a pWell-nActive diode. The connection pin to the pad cell is connected between both diodes. 
    </p>
<p align="center">
  <img width="250" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/968d4408-8881-4ef7-af7e-70039c00e266">
<p align="center">Figure 2 (Schematic of the pad cell with ESD protection in Electric VLSI)</p>
    <p>    
        An icon was then generated from the schematic. This is an important step as the icon will be used to quickly build the padframe schematic.
    </p>
<p align="center">
  <img width="400" height="375" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/4a4f7a4e-b07e-4624-a412-bc7572ad5d1b">
</p>
<p align="center">Figure 3 (Icon generated from the pad cell with ESD protection in Electric VLSI)</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="cellLay"></a></dd></dl> 

<dl><dd><dl><dd><p>
    <p>    
        The layout for the pad cell was created using the provided pWell-nAcitve and pActive-nWell diode layouts as well as the pad cell layout. The pActive-nWell diode is connected to the pad cell and a metal one contact that acts as the voltage export. The pWell-nActive diode is connected to the pad cell and a metal one-to-metal two contact. From the contact, a metal two layer connects to another metal one-contact that acts as the ground export. The metal two layer connected to the pWell-nActive diode will act as a bridge over the voltage bus in the padframe layout. The input/output pin is connected between the two diodes on the metal two layer of the pad cell. 
    </p>
<p align="center">
  <img width="325" height="500" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/0ae45432-c1fe-41d4-857e-ba36e2a3f9ca">
</p>
<p align="center">Figure 4 (Layout of the pad cell with ESD protection created in Electric VLSI)</p>

<p>    
    The 3D view of the layout provides a clearer display of the diodes and how they are oriented. The overglass is rendered as if it is hovering over the metal two layer. This is not the case, this is just a graphical feature. 
</p>
<p align="center">
  <img width="550" height="425" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/927dae64-75cc-4bad-95e0-b55140a4432d">
</p>
<p align="center">Figure 5 (3D view of the layout created in Electric VLSI)</p>

</p></dd></dl></dd></dl>

<h2>Padframe with ESD Protection</h2> <a name="padframe"></a>

<dl><dd><h3>Schematic</h3> <a name="padframeSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>The padframe with ESD protection schematic was created using the pad icon. The icon is connected to a bus with eight exports named, pin[1] through pin[8]. Eight pins are required in this design as the NMOS transistor will have four outputs and inputs, and an additional pad is required for a voltage connection.</p>
<p align="center">
  <img width="425" height="350" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/ea17ac8b-08bb-4846-9671-cea8d7d0b554">
</p>
<p align="center">Figure 6 (Schematic of the padframe with ESD protection in Electric VLSI)</p>
    <p>An icon was then generated from the schematic. This is an important step as the icon will be used in the final IC schematic.</p>
<p align="center">
  <img width="400" height="300" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/87b0d755-d2ec-4b8b-bea6-51426861b3dd">
</p>
<p align="center">Figure 7 (Icon of the padframe with ESD protection schematic in Electric VLSI)</p>

</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="padframeLay"></a></dd></dl> 
<dl><dd><dl><dd>
    <p>The padframe layout was created using eight pad cell layouts with ESD protection. Each pad cell's vdd and gnd exports were connected together through a ground and voltage bus. An export was then created on each bus for ground and voltage.</p>
    <p align="center">
      <img width="450" height="450" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/d5ce5da1-6509-495e-a536-4567785f2e9d">
    </p>
<p align="center">Figure 8 (Layout of the padframe with ESD protection in Electric VLSI)</p>
    <p>The 3D view of the layout provides a clearer display of how the pad cells are connected together</p>
    <p align="center">
      <img width="600" height="475" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/470f6254-ab52-48a9-a701-a74437986093">
    </p>
<p align="center">Figure 9 (3D view of the layout in Electric VLSI)</p>
</dd></dl></dd></dl>

<h2> Final IC with ESD Protection</h2> <a name="padDac"></a>

<dl><dd><h3>Schematic</h3> <a name="padDacSchem"></a></dd></dl> 

<dl><dd><dl><dd>
    
<p>The schematic of the final IC with ESD protection made use of the padframe and NMOS transistor icons. The transistor is connected to the padframe using pins two through six. The voltage bus on the padframe is connected to pin 5, and ground is connected to pin 6.</p>
<p align="center">
  <img width="700" height="400" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/fc638277-2d97-4faf-a7c9-06f640015134">
</p>
<p align="center">Figure 10 (Schematic of the padframe with ESD protection connected to an NMOS transistor)</p>
</dd></dl></dd></dl>

<dl><dd><h3>Layout</h3> <a name="padDacLay"></a></dd></dl> 
<dl><dd><dl><dd>
    <p>The final IC layout consists of the padframe with ESD protection layout and the NMOS transistor layout. The outputs/inputs are connected to their respective pins based on the schematic. These connections are down by using metal one to metal two vias. Pins five and six are connected to their respective buses. </p>
    <p align="center">
      <img width="550" height="550" src="https://github.com/tobywerthan/ENCE_3501_VLSI_2023/assets/55803740/9694a9c1-8f6d-4be5-8713-05e7446aa646">
    </p>
<p align="center">Figure 11 (Layout of the padframe with ESD protection connected to an NMOS transistor)</p>
    <p>The 3D view of the layout provides a clearer display of the padframe, ESD protection, and how it connects to the NMOS transistor.</p>
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
    Connecting each pad cell to this simple ESD protection circuit provides some defense against ESD for the internals of the IC. This design can be used in further projects for more complex circuits, and padframes can be created from this library that incorporate more complex ESD protection as well. Lab 4 dives further into the use of transistors for the design of pullup and pulldown networks for logic gates, specifically, the inverter. 
</div>
