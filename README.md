# Memristive Crossbar Array with CMOS Inverter Activation Function
A project demonstrating a memristive crossbar array integrated with CMOS inverters to implement the tanh activation function for efficient neural network computation. This design explores a hybrid approach to achieve analog computation within a hardware neural network framework, leveraging the advantages of memristive devices and CMOS technology.
## Introduction
This project demonstrates a hardware neural network architecture using a memristive crossbar array for efficient parallel computation. A CMOS inverter pair serves as the activation function, approximating the hyperbolic tangent (tanh) non-linearity. This project includes:

1. Schematic design in Xschem
2. Simulation in ngspice to verify the circuit functionality
3. Transient analysis for response verification
## Features
1. Memristive Crossbar Array: Analog matrix multiplication using memristive properties for weight storage.
2. CMOS Activation: A CMOS inverter pair implements the tanh activation function.
3. Simulation with ngspice: Schematic and performance analysis to verify the activation and analog computation.
## Circuit Design
The crossbar array has the following configuration:

1. Word Line (WL) connected to the gates of two nFETs, receiving a pulse wave input.
2. Source Line (SL) connected to the source of one nFET and the drain of the other, receiving the same pulse input as WL.
3. Resistor in series with the drain-source path, with the opposite end named Bit Line (BL).
4. BL connected to a CMOS inverter, which feeds into another inverter for output.
5. This design structure enables analog multiplication and a hardware-based activation function suitable for neuromorphic and edge computing applications.

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

### Transient Analysis
Open the project file in ngspice.
Run the following command for transient simulation:
```
.tran 100p 10n
plot v(Vout)
```
## Future Work

1. To use layout tool like Magic or KLayout to create a physical layout for the design.
2. To perform post-layout simulation in ngspice (or another tool) to see the effects of parasitics and physical layout on the design's performance.
3. Implementing a feedback mechanism that enables real-time adjustments to the memristor weights, allowing the array to adapt dynamically.
4. Focusing on low-power design strategies to make the circuit suitable for edge AI applications by minimizing energy consumption while maintaining efficiency.
5. Expanding the crossbar array to support multi-layer neural networks, enhancing computational capabilities and enabling more complex operations.
6. To integrate on-chip training using memristive learning rules to allow the network to learn and adapt over time, supporting efficient hardware-based machine 
   learning.

## Contributors

- **Adithya Das** 
  



## Acknowledgments


- Kunal Ghosh, Director, VSD Corp. Pvt. Ltd.
- Megha R, Student , Digital University Kerala
- Vineetha Vasudhevan Nair, PhD, Digital University Kerala




