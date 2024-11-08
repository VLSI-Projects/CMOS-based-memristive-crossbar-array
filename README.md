# Memristive Crossbar Array with CMOS Inverter Activation Function
A project demonstrating a memristive crossbar array integrated with CMOS inverters to implement the tanh activation function for efficient neural network computation. This design explores a hybrid approach to achieve analog computation within a hardware neural network framework, leveraging the advantages of memristive devices and CMOS technology.
## Introduction
This project demonstrates a hardware neural network architecture using a memristive crossbar array for efficient parallel computation. A CMOS inverter pair serves as the activation function, approximating the hyperbolic tangent (tanh) non-linearity. This project includes:

1. Schematic design in Xschem
2. Simulation in ngspice to verify the circuit functionality
3. Transient analysis for response verification
## Features
The project features a memristive crossbar array that enables analog matrix multiplication by utilizing the unique properties of memristive devices for weight storage.A CMOS inverter pair is used to implement the tanh activation function, providing a hardware-based analog solution for non-linear activation in neural networks.The design is fully simulated with ngspice, where schematic and performance analyses are conducted to verify the functionality of the activation and analog computation, ensuring the system operates as intended.
## Component Specification Table

| **Component**               | **Description**                                                             | **Max Value**                           | **Min Value**                           | **Typical Value**                      | **Unit**            | **Temperature Range**        |
|-----------------------------|-----------------------------------------------------------------------------|-----------------------------------------|-----------------------------------------|----------------------------------------|---------------------|------------------------------|
| **nFET** (4)                | N-channel MOSFET, used for switching operations in the memristive array       | Vgs: 3.3V, Vds: 3.3V, Ids: 1mA         | Vgs: 0V, Vds: 0V, Ids: 0A               | Vgs: 1.8V, Vds: 1.8V, Ids: 0.5mA       | V, A                | -40°C to 125°C                |
| **pFET** (2)                | P-channel MOSFET, used in combination with nFETs for the crossbar array       | Vgs: -3.3V, Vds: -3.3V, Ids: 1mA       | Vgs: 0V, Vds: 0V, Ids: 0A               | Vgs: -1.8V, Vds: -1.8V, Ids: 0.5mA     | V, A                | -40°C to 125°C                |
| **Resistor** (2)            | Series resistors in the crossbar array and the output path                   | 10MΩ                                   | 1kΩ                                      | 2kΩ                                    | Ω                  | -40°C to 125°C                |
| **Voltage Source** (4)      | Supply and signal voltage sources for simulation                             | 3.3V, 1.8V, 0V                         | 0V                                       | 1.8V, 3.3V, 0V                        | V                   | -40°C to 125°C                |
| **Pulse Wave Source** (2)   | Pulse wave voltage sources driving the WL and SL                              | 3.3V (High), 0V (Low)                  | 0V                                       | 1.8V (High), 0V (Low)                  | V                   | -40°C to 125°C                |
| **CMOS Inverter** (2)       | Inverters used for activation function (tanh)                                | Vdd: 1.8V                              | Vss: 0V                                 | Vdd: 1.8V, Vss: 0V                     | V                   | -40°C to 125°C                |
| **Memristor**               | Non-volatile memory element for weight storage                               | 10MΩ                                   | 1kΩ                                      | 100kΩ                                  | Ω                  | -40°C to 125°C                |
| **CMOS Inverter Propagation Delay** | Delay associated with CMOS inverter switching                             | 50ns                                   | 5ns                                      | 20ns                                   | Time                | -40°C to 125°C                |
| **Chip Area**               | Total area of the chip (estimated)                                           | 5mm²                                    | 1mm²                                     | 3mm²                                   | mm²                 | N/A                          |
| **Operating Frequency**     | Maximum frequency at which the design can operate                           | 100 MHz                                | 10 MHz                                   | 50 MHz                                  | Hz                  | -40°C to 125°C                |
| **Power Consumption**       | Power consumption of the entire design                                       | 500mW                                  | 10mW                                    | 200mW                                  | Watts               | -40°C to 125°C                |
| **Input Pulse Frequency**   | Frequency of pulse wave inputs for WL and SL lines                           | 500 MHz                                | 10 MHz                                   | 100 MHz                                 | Hz                  | -40°C to 125°C                |

### Key Parameters for Simulation:
- **Pulse Wave Parameters**: `pulse(1 0.5n 100p 100p 1n 2n)`
  - **High Level (1)**: 3.3V
  - **Low Level (0)**: 0V
  - **Rise Time**: 100ps
  - **Fall Time**: 100ps
  - **Pulse Width**: 1ns
  - **Period**: 2ns
- **Supply Voltage (Vdd)**: 1.8V for CMOS inverters, 3.3V for signal sources
- **Resistor Value**: 2kΩ for the series resistors in the crossbar array

## Circuit Design
The crossbar array is configured with the Word Line (WL) connected to the gates of two nFETs, receiving a pulse wave input. The Source Line (SL) is connected to the source of one nFET and the drain of the other, both receiving the same pulse input as WL. A resistor is placed in series with the drain-source path, and its opposite end is named the Bit Line (BL). The BL is connected to a CMOS inverter, which in turn feeds into another inverter for the final output. This design structure allows for analog matrix multiplication and incorporates a hardware-based activation function, making it well-suited for neuromorphic computing and edge AI applications.
### Advantages of this design
1. Enables fast, analog matrix multiplication for neural networks.
2. Allows for easy expansion to multi-layer neural networks with minimal chip area increase.
3. Low Power Consumption.
4. Supports high-throughput, real-time computations.
5. Implements tanh activation function directly in hardware for faster performance.
6. Mimics biological neural networks for efficient processing.
7. Ideal for low-power, fast processing in edge AI applications.

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

## Conclusion
In conclusion, this project demonstrates the integration of a memristive crossbar array with CMOS inverters to implement an efficient hardware-based activation function for neural networks. By leveraging the unique properties of memristive devices for weight storage and using CMOS technology for the tanh activation, the design offers a compact, low-power, and scalable solution suitable for neuromorphic computing. The use of analog computation and parallel processing enhances the speed and efficiency of neural network operations, making it ideal for edge AI applications. This approach opens new avenues for energy-efficient, high-performance hardware accelerators in real-time machine learning tasks.
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

## Reference
https://www.engineerwikis.com/wikis/installation-of-xschem
https://rdcu.be/dZzIK

