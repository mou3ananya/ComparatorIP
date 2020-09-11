# ComparatorIP
This repository contains a structural as well as functional description of a comparator with 3.3v analog voltage. This repository will maintain simulation files and other relevant files on the pre-mentioned design block worked on in the Online VSD IP Design Research Internship program 2020.

*Note: Circuit requires further optimization to improve performance. Design yet to be modified.*


Table of contents
=================
<!--ts-->
   * [A Glance at the Comparator IP](#a-glance-at-the-comparator-ip)
        * [Block Diagram of the Comparator IP](#block-diagram-of-the-comparator-ip)
        * [Internal Block Diagram of the Comparator IP](#internal-block-diagram-of-the-comparator-ip)    
   * [Circuit Diagram of the Comparator IP](#circuit-diagram-of-the-comparator-ip)
        * [Circuit Diagram of each sub-block](#circuit-diagram-of-each-sub--block)
   * [Running the Simulation](#running-the-simulation)
   * [Pre-Layout Simulation result](#pre-layout-simulation-result)Pre-Layout Simulation result for each block
        * [Pre-Layout Simulation result for each block](#pre-layout-simulation-result-for-each-block)
   * [Issues | Improvements | Future Work](#issues--improvements--future-work)
   * [Open-Source VLSI Tools](#open-source-vlsi-tools)
       * [About Ngspice](#about-ngspice)
   * [Acknowledgments](#acknowledgments)
   * [Contact Information](#contact-information)
<!--te-->

## A Glance at the Comparator IP

The  Design Specifications of the Comparator IP can be found [here](/Documentations/specs.pdf).

### Block Diagram of the Comparator IP

 <p align="center">
  <img width="850" height="550" src="/Images/comp_blk.jpg">
</p>



### Internal Block Diagram of the Comparator IP

The Comparator IP is built using 5 important circuit sub-components:
1. [Biasing Circuit](#biasing-circuit)
2. [Differential Pair with level shifter where i/p is applied to NMOS](#differential-pair-with-level-shifter-where-i/p-is-applied-to-nmos)
3. [Differential Pair with level shifter where i/p is applied to PMOS](#differential-pair-with-level-shifter-where-i/p-is-applied-to-pmos)
4. [CMOS Inverter circuit](#cmos-inverter-circuit)
5. [CMOS OR Logic circuit](#cmos-or-logic-circuit)




 <p align="center">
  <img width="900" height="550" src="/Images/comp_int.PNG">
</p>



## Circuit Diagram of the Comparator IP


 <p align="center">
  <img width="850" height="500" src="/Images/comp_ckt.PNG">
</p>


## Subcircuits within the Comparator IP

### Differential Pair with En pin and single i/p applied to NMOS

<p align="center">
  <img width="850" height="550" src="/Images/blk1.PNG">
</p>

<p align="center">
  <img width="850" height="550" src="/Images/blk_b1.PNG">
</p>

### CMOS Inverter block 

<p align="center">
  <img width="350" height="550" src="/Images/blk2.PNG">
</p>

<p align="center">
  <img width="850" height="550" src="/Images/blk_b2.PNG">
</p>

### Differential Pair with 2 i/ps applied to NMOS where the En is the o/p of the 1st differential single i/p block 

<p align="center">
  <img width="850" height="550" src="/Images/blk3.PNG">
</p>

<p align="center">
  <img width="850" height="550" src="/Images/blk_b3.PNG">
</p>

### Differential Pair with 2 i/ps applied to PMOS where the En is the o/p of the 1st differential single i/p block 

<p align="center">
  <img width="850" height="550" src="/Images/blk4.PNG">
</p>

<p align="center">
  <img width="850" height="550" src="/Images/blk_b4.PNG">
</p>

### CMOS OR Logic block

<p align="center">
  <img width="850" height="550" src="/Images/blk5.PNG">
</p>

<p align="center">
  <img width="850" height="550" src="/Images/blk_b5.PNG">
</p>


## Running the Simulation


To enter the Ngspice Shell, open the terminal & type:
```
$ ngspice
```
To simulate a netlist, type:
```
ngspice 1 ->  <filename>.cir
```

You can exit from the Ngspice Shell by typing:
```
ngspice 1 ->  exit
```
 <p align="center"> or </p>
 
```
ngspice 1 ->  quit
```

## Pre-Layout Simulation

To clone the Repository and download the Netlist files for Simulation, enter the following commands in your terminal.

```
$  sudo apt install -y git
$  git clone https://github.com/mou3ananya/ComparatorIP
$  cd ComparatorIP/simulation/preLayout/
```
### Waveform Analysis of Comparator circuit 

```
Open the comparator.cir file. Here the difference between 2 i/p signals is 0.5mV. You can take any other combinations for i/p voltages also by entering the i/p signals as shown in the image below.
```

 <p align="center">
  <img width="750" height="100" src="/Images/input.PNG">
</p>

Run the netlist file using the following command.

```
$  ngspice comparator.cir
```

Observe the corresponding waveforms

#### Inverting (v_n) and Non-inverting (v_p) i/p waveforms

<p align="center">
  <img width="1000" height="600" src="/Images/w_comp1">
</p>

#### En (Enable Active High) i/p waveform

<p align="center">
  <img width="1000" height="600" src="/Images/w_comp3">
</p>

#### Comparator o/p waveform

<p align="center">
  <img width="1000" height="600" src="/Images/w_comp2">
</p>

```
When En='1'[3.3v], o/p[OUT] follows the Non-inverting i/p[v_p]  
If En='0' then whole IP becomes off 
During OFF state o/p remains at logic '0'

```

### Pre-Layout Simulation result for each block





