# CMOS-based-memristive-crossbar-array
This project presents the design and simulation
of a CMOS-based static random-access memory (SRAM) cell,
employing a six-transistor (6T) configuration for efficient data
storage and retrieval.


## A glance at CMOS-based-memristive-crossbar-array with tanh activation function
Static random-access memory (SRAM) is a crucial compo-
nent in modern digital systems, offering high-speed data access
and stability compared to dynamic random-access memory
(DRAM). This report discusses the design of a CMOS-based
SRAM cell, specifically a 6T configuration, which is widely
used in memory arrays. The design integrates access transistors
and cross-coupled inverters to facilitate robust data storage
and retrieval capabilities. We aim to explore the operational
characteristics of the SRAM cell through detailed circuit
analysis and simulation, highlighting its potential applications
in various computing environments.




## A Glance at the Bandgap Reference IP

To learn more about , its principle of generation, Implementation, Issues & Improvements, consider reading [this](/Documentation/BGR.pdf).

To gain insight into the applications and significance of Bandgap Reference in VLSI, have a look at [this](/Documentation/Applications.pdf).

To review the previous Bandgap Reference Design, read [this](/Documentation/README_old_1.0.md).

The  Design Specifications of the Bandgap Reference Circuit can be found [here](/Documentation/Specifications.pdf).


## Block Diagram of the Bandgap Reference IP

 <p align="center">
  <img width="800" height="500" src="/Images/N/block.png">
</p>




## Circuit Diagram of the Bandgap Reference IP

 <p align="center">
  <img width="800" height="500" src="/Images/N/circuit.png">
</p>

## Layout of the Bandgap Reference IP

### Layout of the Complete Bandgap Reference Block with Start-up & Power Down

 <p align="center">
  <img width="600" height="700" src="/Images/N/layout.png">
</p>

### Layout of Vertical Parasitic PNP BJT

 <p align="center">
  <img width="500" height="400" src="/Images/N/bjt.png">
</p>

## Modification to the Technology File

**To ensure that the Vertical Parasitic PNP BJT was recognized and extracted correctly, the line below was added to the Technology File.**

```
 device bjt PNP nwell,nsc/a,nsd pdiff,pdc/a pwell,space/w,psc/a,psd 
```

## Bandgap Performance Parameters [Post-Layout]

| Parameter| Description| Min | Type | Max | Unit | Condition |
| :---:  | :-: | :-: | :-: | :---:  | :-: | :-: |
|Technology| 0.18 µm CMOS Process |
|RL|Load resistance at Vbgp terminal | 100|||Mohm|VDD=3.3V, T=27C|
|CL|Load capacitance at Vbgp terminal|||50|pF|VDD=2.7V - 3.6V, T=-40C - 125C, RL=100M|
|Vbgp|Output Reference voltage|1.2013 |1.2056|1.2070|V|T=-40 to 140C, VDD=3.3V|
|Vbgp|Output Reference voltage|1.1698 |1.2056|1.2234|V|VDD=2.7V to VDD=3.6V, T=27C|
|TC_vbgp|Temperature Coefficient of Vbgp||26.2663||ppm/C|T=-40 to 125C, VDD=3.3V|
|VC_vbgp|Voltage Coefficient of Vbgp||5.9555||%/V|VDD=2.7V to 3.7, T=27C|
|Tstart|Start up time||3.3||us|Vdd=3.3V, T=27C, CL=50pF|
|VDD|Supply Voltage|3.2|3.3|3.6|V|T=-40C to 125C|
|IDD|Supply Current||22.4760||uA|EN=1|
|IDD|Supply Current||95.3950||pA|EN=0|

## Pre-Layout Performance Characteristics

###  Vbgp v/s Temperature [ -40C - 140C] @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/PRE/pre_temp.png">
</p>


###  Vbgp v/s VDD [ 2V - 4V] @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/PRE/pre_supply.png">
</p>

###  Temperature Coefficient of Vbgp v/s Temperature [ -40C - 140C] @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/PRE/pre_tc.png">
</p>

###  Voltage Coefficient of Vbgp v/s VDD [ 2V - 4V] @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/PRE/pre_vc.png">
</p>

###  Start-Up Time of Vbgp @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/PRE/pre_startup.png">
</p>


###  On-Off-Current of Vbgp wrt Enable @ RL = 100M ohms plot

 <p align="center">
  <img width="1000" height="500" src="/Images/N/PRE/pre_c.png">
</p>

**Note:Current without Inverter for Enable Logic**

## PostLayout Performance Charcateristics

###  Vbgp v/s Temperature [ -40C - 140C] @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/POST/post_temp.png">
</p>


###  Vbgp v/s VDD [ 2V - 4V] @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/POST/post_supply.png">
</p>

###  Temperature Coefficient of Vbgp v/s Temperature [ -40C - 140C] @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/POST/post_tc.png">
</p>

###  Voltage Coefficient of Vbgp v/s VDD [ 2V - 4V] @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/POST/post_vc.png">
</p>



###  Start-Up Time of Vbgp @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/POST/post_startup.png">
</p>


###  On-Off-Current of Vbgp wrt Enable @ RL = 100M ohms plot

 <p align="center">
  <img width="1100" height="500" src="/Images/N/POST/post_c.png">
</p>

**Note:Current without Inverter for Enable Logic**


<img align="left" width="60" height="50" src=/Images/ng_logo.png>




## About Ngspice 
Ngspice is an open source mixed-signal circuit simulator.

### Installing Ngspice

#### For Ubuntu

Open your terminal and type the following to install Ngspice
```
$  sudo apt-get install -y ngspice
```

## Running the Simulation


To enter the Ngspice Shell, open the terminal & type:
```
$ ngspice
```
To simulate a netlist, type:
```
ngspice 1 ->  source <filename>.cir
```

You can exit from the Ngspice Shell by typing:
```
ngspice 1 ->  exit
```
 <p align="center"> or </p>
 
```
ngspice 1 ->  quit
```

There are several waveforms that need to be obtained to observe the performance of the Bandgap reference circuit.

### Pre-Layout Simulation

To clone the Repository and download the Netlist files for Simulation, enter the following commands in your terminal.

```
$  sudo apt install -y git
$  git clone https://github.com/sherylcorina/avsdbgp_3v3
$  cd avsdbgp_3v3/Simulation/Ngspice_Simulation/Final_Simulation/PreLayout
```




### To obtain the Vbgp v/s Temperature [ -40C - 140C] @ RL = 100M ohms plot


Run the netlist file using the following command.
```
$  ngspice pre_temp.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/pre_ps_temp.png">
</p>


### To obtain the Vbgp v/s VDD [ 2V - 4V ] @ RL = 100M ohms plot

Run the netlist file using the following command.
```
$  ngspice pre_supply.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/pre_ps_supply.png">
</p>

### To obtain the Temperature Coefficient of Vbgp v/s Temperature [ -40C - 140C] @ RL = 100M ohms plot

Run the netlist file using the following command.
```
$  ngspice pre_tc.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/pre_ps_tc.png">
</p>

### To obtain the Voltage Coefficent of Vbgp v/s VDD [ 2V - 4V ] @ RL = 100M ohms plot

Run the netlist file using the following command.
```
$  ngspice pre_vc.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/pre_ps_vc.png">
</p>

### To obtain the Start Up Time plot


Run the netlist file using the following command.
```
$  ngspice pre_startup.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/pre_ps_startup.png">
</p>


###  On-Off-Current of Vbgp wrt Enable [1 -> 0] @ RL = 100M ohms plot


Run the netlist file using the following command.
```
$  ngspice pre_enable.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/pre_ps_startup.png">
</p>

**Note:Current without Inverter for Enable Logic**

***************

### Post-Layout Simulation

Ensure the Repository with the Simulation Files is cloned. Review the section above for detailed steps.
Enter the following command in your terminal.
```
$  cd avsdbgp_3v3/Simulation/Ngspice_Simulation/Final_Simulation/PostLayout
```


### To obtain the Vbgp v/s Temperature [ -40C - 140C] @ RL = 100M ohms plot


Run the netlist file using the following command.
```
$  ngspice post_temp.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/post_ps_temp.png">
</p>


### To obtain the Vbgp v/s VDD [ 2V - 4V ] @ RL = 100M ohms plot

Run the netlist file using the following command.
```
$  ngspice post_supply.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/post_ps_supply.png">
</p>

### To obtain the Temperature Coefficient of Vbgp v/s Temperature [ -40C - 140C] @ RL = 100M ohms plot

Run the netlist file using the following command.
```
$  ngspice post_tc.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/post_ps_tc.png">
</p>

### To obtain the Voltage Coefficent of Vbgp v/s VDD [ 2V - 4V ] @ RL = 100M ohms plot

Run the netlist file using the following command.
```
$  ngspice post_vc.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/post_ps_vc.png">
</p>

### To obtain the Start Up Time plot


Run the netlist file using the following command.
```
$  ngspice post_startup.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/post_ps_startup.png">
</p>


###  On-Off-Current of Vbgp wrt Enable [1 -> 0] @ RL = 100M ohms plot


Run the netlist file using the following command.
```
$  ngspice post_enable.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/post_ps_startup.png">
</p>

**Note:Current without Inverter for Enable Logic**

## Future Work

1. Improved matching techniques such as Common Centroid / Interdigitisation need to be implemented while laying out the current mirror.
2. PNR for the designed circuit is yet to performed using the Open Source Tool provided by the OpenROAD project.
3. Corner Analysis Testing of the bandgap reference circuit is yet to be performed.
4. The load driving capability needs to be improved by addition of a buffer block such as an OTA or a common drain amplifier.
5. To adjust the reference voltage resistors must be trimmed using fuses, hence, resistor trimming must be employed in the circuit.
6. The design must be improved to provide a higher PSRR.
7. In the future an OTA based bandgap reference circuit will be developed with improved performance characteristics. Also, a second order bandgap reference will be studied and developed, to improve the temperature coefficient.
8. To solve the problem of unwanted parasitic BJTs being extracted due to the modification made in the Technology File.

## Contributors

- **Adithya Das** 
  



## Acknowledgments


- Kunal Ghosh, Director, VSD Corp. Pvt. Ltd.
- Megha R, Student , Digital University Kerala
- Vineetha Vasudhevan Nair, PhD, Digital University Kerala




