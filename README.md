# CMOS_SRAM-and-RCA_Layout-Sim
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This project focuses on designing and verifying a 6T SRAM cell and a 4-bit Ripple Carry Adder layout using Magic VLSI for layout design and IRSIM for simulation. The objective is to ensure that the design is DRC error-free and the functionally correctness. This documentation provides a detailed explanation of the design steps, layout process, verification, and simulation results.

# Overview of SRAM and Ripple Carry Adder

**Static Random-Access Memory (SRAM)** is widely used in caches and memory applications due to its fast access time. The 6T SRAM cell is a standard memory cell design using six transistors. The **4-bit Ripple Carry Adder (RCA)** is a fundamental arithmetic circuit used in microprocessors and digital systems.

## Tools Used

• **Magic VLSI:** Open-source tool for layout design and DRC checking. <br>
• **IRSIM:** Simulator for verifying the circuit's logical behavior. <br>

## Design Specifications

• **6T SRAM Cell:** CMOS-based layout ensuring minimal area and stable operation. <br>
• **4-bit Ripple Carry Adder:** Designed using full adders cascaded to perform multi-bit addition. <br>
• **Zero DRC Errors:** Ensured layout is clean and meets foundry design rules.


# 6T SRAM Cell Layout  
## Circuit Diagram 
#### The 6T SRAM cell consists of: 

• Two cross-coupled inverters for storage. <br>
• Two NMOS access transistors for read/write operations.

                            
![pro](https://github.com/JagadeeshAJK/CMOS_SRAM-and-RCA_Layout-Sim/blob/main/6T-SRAM-Cell.png)

M1, M2, M3, M4: form two cross-coupled CMOS inverters.These create a latch that holds either ‘0’ or ‘1`<br>
M5 and M6: access transistors (usually NMOS) controlled by the Word Line (WL) and connect the cell to Bit Line (BL) and Bit Line Bar (BLB) during read/write



#### 1. Hold Operation :
• WL = 0 → access transistors (M5, M6) are OFF <br>
• The two inverters (M1–M4) are cross-coupled.They keep feeding each other and data is held indefinitely without refreshment.<br>
**Result  :** Stored bit remains unchanged.



#### 2. Write Operation:
• Set BL and BLB to desired value:<br>
• To write '1':    <br>
 &nbsp;&nbsp;&nbsp; WL = 1 → access transistors ON <br>
 &nbsp;&nbsp;&nbsp;     BL = 1, BLB = 0 <br>
• Strong drivers on bit lines overwrite the inverters' state and Forces Q and QB to switch cross-coupled inverters latch new value<br>
**Result :** New data is written into the cell.






#### 3. Read Operation :
• keep BL and BLB as x and WL = 1 → access transistors turn ON<br>
• Stored data appears on BL/BLB:<br>
• If cell stores ‘1’ then BL stays high and BLB stays Low.<br>
**Result :** Data is read without disturbing the stored value.






![pro](https://github.com/JagadeeshAJK/CMOS_SRAM-and-RCA_Layout-Sim/blob/main/tool_sram.png)
![pro](https://github.com/JagadeeshAJK/CMOS_SRAM-and-RCA_Layout-Sim/blob/main/irsim_sram.png)
![pro](https://github.com/JagadeeshAJK/CMOS_SRAM-and-RCA_Layout-Sim/blob/main/Sram_sim.png)
#  4-bit Ripple Carry Adder Layout
## Circuit Diagram
• The RCA is built using four cascaded full adders. <br>
• A full adder consists of two XOR gates, three NAND gates.

![pro](https://github.com/JagadeeshAJK/CMOS_SRAM-and-RCA_Layout-Sim/blob/main/converted.jpg)
### 4-bit Ripple Carry Adder Operation:
• A 4-bit RCA consists of 4 full adders connected in series. <br>
• It adds two 4-bit binary numbers and one carry-in.<br>
• Each full adder adds one bit from each number plus a carry-in, producing a sum bit and a carry-out.<br>
• The carry-out of each stage ripples to the next stage as carry-in.<br>
• The final output is a 4-bit sum and one carry-out.

### Inputs:
A0, A1, A2, A3 → Bits of input A (LSB to MSB)<br>
B0, B1, B2, B3 → Bits of input B<br>
C0 → Initial carry input (usually 0)

### Operation (per full adder):
#### FA0:
S0 = A0 + B0 + C0<br>
**→ Outputs:** Sum S0, Carry C1
#### FA1:
S1 = A1 + B1 + C1<br>
**→ Outputs**: Sum S1, Carry C2
#### FA2:
S2 = A2 + B2 + C2<br>
**→ Outputs:** Sum S2, Carry C3
#### FA3:
S3 = A3 + B3 + C3<br>
**→ Outputs:** Sum S3, Carry C
### Final Outputs:
**Sum =**  S3 S2 S1 S0<br>
**Carry-out =** C


![pro](https://github.com/JagadeeshAJK/CMOS_SRAM-and-RCA_Layout-Sim/blob/main/tool_adder.png)
![pro](https://github.com/JagadeeshAJK/CMOS_SRAM-and-RCA_Layout-Sim/blob/main/irsim_adder.png)
![pro](https://github.com/JagadeeshAJK/CMOS_SRAM-and-RCA_Layout-Sim/blob/main/Adder_sim.png)
