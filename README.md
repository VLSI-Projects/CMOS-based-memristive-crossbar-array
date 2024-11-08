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

## Installation of Xschem, Skywater130 PDK and Ngspice

### About Xschem
Xschem is a schematic capture program, it allows creation of hierarchical representation of circuits with a top down approach . By focusing on interfaces, hierarchy and instance properties a complex system can be described in terms of simpler building blocks.
### Installing xschem

#### For Ubuntu
Open your terminal and type the following to install Ngspice
```
$  sudo apt-get install -y xschem
```
#### git Installation
```
$  sudo apt-get update
$  sudo apt-get upgrade
$  sudo apt-get install git-all
```

To clone the Xschem from GitHub repo:
```
$  git clone https://github.com/StefanSchippers/xschem.git xschem-git
$  cd xschem-git
```
#### Package Installation
```
$  sudo apt-get install libx11-6
$  sudo apt-get install libx11-dev
$  sudo apt-get install libxrender1
$  sudo apt-get install libxrender-dev
$  sudo apt-get install libxcb1
$  sudo apt-get install libx11-xcb-dev
$  sudo apt-get install libcairo2
$  sudo apt-get install libcairo2-dev
$  sudo apt-get install tcl8.6
$  sudo apt-get install tcl8.6-dev
$  sudo apt-get install tk8.6
$  sudo apt-get install tk8.6-dev
$  sudo apt-get install flex
$  sudo apt-get install bison
$  sudo apt-get install libxpm4
$  sudo apt-get install libxpm-dev
$  sudo apt-get install gawk
$  sudo apt-get install mawk
$  sudo apt-get install tcl-tclreadline
$  sudo apt-get install xterm
```
#### install xschem
```
$  ./configure
$  sudo -i
$  cd /home/parallels/Desktop/xschem-git
$  make
$  make install
```
### Install Skywater130 PDK
```
$  cd /home/parallels/Desktop
$  git clone https://github.com/google/skywater-pdk
$  cd skywater-pdk
$  git submodule init libraries/sky130_fd_io/latest
$  git submodule init libraries/sky130_fd_pr/latest
$  git submodule init libraries/sky130_fd_sc_hd/latest
$  git submodule init libraries/sky130_fd_sc_hdll/latest
```
# optional -----------

```
$  git submodule init libraries/sky130_fd_sc_hs/latest
$  git submodule init libraries/sky130_fd_sc_ms/latest
$  git submodule init libraries/sky130_fd_sc_ls/latest
$  git submodule init libraries/sky130_fd_sc_lp/latest
$  git submodule init libraries/sky130_fd_sc_hvl/latest
# --------------------
```
# You can skip the above optional command. But the following two commands must be run.
```
$  git submodule update
$  make timing
```
## About Ngspice 
Ngspice is an open source mixed-signal circuit simulator.

### Installing Ngspice

#### For Ubuntu
Open your terminal and type the following to install Ngspice
```
$  sudo apt-get install -y ngspice
```


 #### download Ngspice from its git rep:
``` 
$  cd /home/parallels/Desktop
$  git clone https://github.com/ngspice/ngspice.git
$  cd ngspice
$  ./autogen.sh --adms
$  mkdir release
$  cd release
```
#### Configure and install Ngspice:
```
$  ../configure  --with-x --with-readline=yes --disable-debug
$  make
$  sudo make install
```



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




