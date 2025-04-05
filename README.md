# CMOS_SRAM-and-RCA_Layout-Sim
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This project focuses on designing and verifying a 6T SRAM cell and a 4-bit Ripple Carry Adder layout using Magic VLSI for layout design and IRSIM for simulation. The objective is to ensure that the design is DRC error-free and the functionally correctness. This documentation provides a detailed explanation of the design steps, layout process, verification, and simulation results.

# Overview of SRAM and Ripple Carry Adder

**Static Random-Access Memory (SRAM)** is widely used in caches and memory applications due to its fast access time. The 6T SRAM cell is a standard memory cell design using six transistors. The **4-bit Ripple Carry Adder (RCA)** is a fundamental arithmetic circuit used in microprocessors and digital systems.

## Tools Used

• **Magic VLSI:** Open-source tool for layout design and DRC checking. 

• **IRSIM:** Simulator for verifying the circuit's logical behavior. 

## Design Specifications

• **6T SRAM Cell:** CMOS-based layout ensuring minimal area and stable operation. 

• **4-bit Ripple Carry Adder:** Designed using full adders cascaded to perform multi-bit addition. 

• **Zero DRC Errors:** Ensured layout is clean and meets foundry design rules.


# 6T SRAM Cell Layout  
## Circuit Diagram 
• The 6T SRAM cell consists of: 
• Two cross-coupled inverters for storage. 
• Two NMOS access transistors for read/write operations.

read/write operations.
![pro](https://github.com/JagadeeshAJK/CMOS_SRAM-and-RCA_Layout-Sim/blob/main/6T-SRAM-Cell.png)
#  4-bit Ripple Carry Adder Layout
## Circuit Diagram
• The RCA is built using four cascaded full adders. 
• A full adder consists of two XOR gates, three NAND gates.

![pro](https://github.com/JagadeeshAJK/CMOS_SRAM-and-RCA_Layout-Sim/blob/main/converted.jpg)
