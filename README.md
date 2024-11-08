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


| **Component**       | **Type**               | **Description**                                                           | **Value**                         | **Unit**         | **Typical Value**   | **Maximum Rating** | **Minimum Rating** | **Temperature Range** | **Technology**        |
|---------------------|------------------------|---------------------------------------------------------------------------|-----------------------------------|------------------|----------------------|--------------------|--------------------|-----------------------|-----------------------|
| **nFET**            | N-channel FET          | N-channel field-effect transistor used for switching and driving the crossbar array. | -                                 | -                | 1.8V                 | 2.5V               | 0V                 | -40°C to 125°C         | SkyWater 130nm        |
| **pFET**            | P-channel FET          | P-channel field-effect transistor used for switching the crossbar array. | -                                 | -                | 1.8V                 | 2.5V               | 0V                 | -40°C to 125°C         | SkyWater 130nm        |
| **Resistor**        | Passive Component      | Used for current limiting in the memristive crossbar array and ensuring proper signal flow. | 2000                              | Ohms             | 2000                 | -                  | -                  | -40°C to 125°C         | Standard Resistor     |
| **Voltage Source**  | DC Source              | Provides constant 1.8V DC supply to power the circuit and transistors in the design. | 1.8                               | V                | 1.8V                 | 1.8V               | 1.8V               | -40°C to 125°C         | Voltage Source        |
| **Pulse Input**     | Voltage Pulse          | Pulse waveform used for driving the **WL (Word Line)** and **SL (Source Line)** to control the transistors in the crossbar array. | `Pulse(0 1 0.5n 100p 100p 1n 2n)` | -                | -                    | -                  | -                  | -40°C to 125°C         | Custom Pulse Source   |
| **CMOS Inverter**   | Digital Logic          | Used to drive the **BL (Bit Line)** with an inverted signal for the memristive crossbar array. | -                                 | -                | -                    | -                  | -                  | -40°C to 125°C         | CMOS Inverter         |
| **Simulation Time** | Transient Analysis     | Total simulation time for transient analysis. Ensures the circuit's behavior is evaluated over a defined period. | 10n                               | ns               | 10n                  | -                  | -                  | -40°C to 125°C         | Simulation Setup      |
| **Simulation Step** | Time Resolution        | Time resolution for transient analysis, ensuring proper data collection at specified time steps during simulation. | 100p                              | ps               | 100p                 | -                  | -                  | -40°C to 125°C         | Simulation Setup      |

### Descriptions and Technologies:
- **nFET and pFET**: These components are essential for switching and driving the crossbar array. The **nFET** controls the flow of electrons, while the **pFET** controls holes. Both are designed using **SkyWater 130nm** technology.
- **Resistor**: The **2000 Ohm resistor** is used in the design to limit current and ensure proper signal flow in the crossbar array. The typical technology is a **Standard Resistor**.
- **Voltage Source**: The voltage source provides **1.8V** DC to power the transistors and other components. It is a **Voltage Source** used in simulations.
- **Pulse Input**: The **pulse input** waveform (`Pulse(0 1 0.5n 100p 100p 1n 2n)`) is used to control the **WL (Word Line)** and **SL (Source Line)**, which drive the nFETs and pFETs for switching. This is a **Custom Pulse Source**.
- **CMOS Inverter**: The **CMOS inverter** generates the **BL (Bit Line)** output in the crossbar array, using complementary metal-oxide-semiconductor (CMOS) logic. This is a **CMOS Inverter**.
- **Simulation Time**: This defines the total duration for transient analysis, which is set to **10ns** to capture the behavior of the circuit. The **Simulation Setup** defines the time range for analysis.
- **Simulation Step**: The **100ps** step resolution ensures that transient effects are accurately captured during simulation. This is also part of the **Simulation Setup**.

## Circuit Design
The crossbar array is configured with the Word Line (WL) connected to the gates of two nFETs, receiving a pulse wave input. The Source Line (SL) is connected to the source of one nFET and the drain of the other, both receiving the same pulse input as WL. A resistor is placed in series with the drain-source path, and its opposite end is named the Bit Line (BL). The BL is connected to a CMOS inverter, which in turn feeds into another inverter for the final output. This design structure allows for analog matrix multiplication and incorporates a hardware-based activation function, making it well-suited for neuromorphic computing and edge AI applications.

## Schematic Diagram
![Image_Alt](https://github.com/NEOGT11/CMOS-based-memristive-crossbar-array/blob/9dd6a3d4d6fbff22793eb6c26c31240f93b2dabb/XSCHEM-SCHEMATIC.png)


### Advantages of this design
1. Enables fast, analog matrix multiplication for neural networks.
2. Allows for easy expansion to multi-layer neural networks with minimal chip area increase.
3. Low Power Consumption.
4. Supports high-throughput, real-time computations.
5. Implements tanh activation function directly in hardware for faster performance.
6. Mimics biological neural networks for efficient processing.
7. Ideal for low-power, fast processing in edge AI applications.
## Output Voltage of Memristive Crossbar Array with tanh Activation Function
![Image_Alt](https://github.com/NEOGT11/CMOS-based-memristive-crossbar-array/blob/bac483381f6133b9042a4d3153c6e63834da6112/Ngspice%20simulation-output%20voltage%20graph.png)
## Transient Response of Word Line (WL) Voltage
![Image_Alt](https://github.com/NEOGT11/CMOS-based-memristive-crossbar-array/blob/171f45f58bd7cc5d91970f1486e561036c01e376/Ngspice%20simulation-Gate%20Voltage.png)

## Transient Response of Source Line (SL) Voltage
![Image_Alt](https://github.com/NEOGT11/CMOS-based-memristive-crossbar-array/blob/5b162fc341d05b60885a1460e9567ca3941d9713/Ngspice%20simulation-Vds.png)
## Transient Response of Bit Line (BL) Voltage
![Image_Alt]()
## Voltage Response of Word Line (WL) and Source Line (SL) in Memristive Crossbar Array
![Image_Alt](https://github.com/NEOGT11/CMOS-based-memristive-crossbar-array/blob/b626a996f4d932d3e2ce4b1dedee3e620a8b7199/Ngspice%20simulation-VG%20vs%20VDS.png)
## Transient Response of Memristive Crossbar Array with CMOS Inverter Activation
![Image_Alt]()
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
- Megha R, Student, Digital University Kerala


## Reference
- https://www.engineerwikis.com/wikis/installation-of-xschem
- https://rdcu.be/dZzIK

