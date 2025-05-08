# Low-power-Static-Random-Access-Memory
Designed and analyzed SRAM cells in 4T, 6T, 8T, and low-power 6T configurations, focusing on power consumption, performance, and latency. Evaluated the advantages and limitations of each configuration to enhance the overall efficiency of SRAM memory.
This research investigates the performance characteristics of SRAM (Static Random Access Memory) cells with varying transistor configurations, specifically 4T, 6T, and 8T designs, alongside an exploration of Low-Power SRAM architectures. The study focuses on evaluating power consumption and delay metrics to understand the trade-offs associated with different SRAM configurations. The SRAM cells are analyzed for their potential in memory applications, considering the increasing demand for energy-efficient and high-performance memory solutions. The investigation involves a comprehensive assessment of power efficiency and delay characteristics in order to provide valuable insights into the comparative advantages and limitations of 4T, 6T, and 8T SRAM designs, as well as low-power SRAM alternatives. The findings from this research contribute to the ongoing efforts to optimize memory architectures for diverse applications in modern integrated circuits.
We conducted simulations using Cadence software for the 90nm technology node and demonstrated a power saving of approximately 37%.

II.	INTRODUCTION
A complete industrial 90-nm process was first introduced by Intel in 2003 [Ghani]. With transistor channels around 50 nm in size (50 billionths of a meter), comparable to the smallest micro- organisms, this technology is truly a nanotechnology.
Strained Silicon
The main novelty related to the 90 nm technology is the introduction of strained silicon to speed-up the carrier mobility, which boosts both the n-channel and p-channel transistor performances. It has been known for decades that stretching the silicon lattice improves the carrier mobility, and consequently the device current.
![image](https://github.com/user-attachments/assets/b2ff543e-aeae-4a7b-8a46-93ad21968fb1)

SRAM
![image](https://github.com/user-attachments/assets/3ea7e6df-81d9-4b54-a7b0-a8ed0af9fe0f)

Static random-access memory (static RAM or SRAM) is a type of random-access memory (RAM) that uses latching circuitry (flip-flop) to store each bit. SRAM is volatile memory; data is lost when power is removed.
The term static differentiates SRAM from DRAM (dynamic random-access memory):
●	SRAM will hold its data permanently in the presence of power, while data in DRAM decays in seconds and thus must be periodically refreshed.
●	SRAM is faster than DRAM but it is more expensive in terms of silicon area and cost.
●	SRAM is typically used for the cache and internal registers of a CPU while DRAM is used for a computer's main memory.
Uses of SRAM Memory
SRAM memory can be used in many different places, and this part will tell you the uses of SRAM memory.
Contemporary SRAM Devices
You can find SRAM on general purpose products and chips.
General Purpose Products
-	With an asynchronous interface.
-	With a synchronous interface.
Integrated on Chip
-	As RAM or cache in microcontrollers (usually from 32 bytes to 128 KB).
-	As the main cache in powerful microprocessors (from 8 KB to several megabytes).
-	To store registers and parts of the state-machines used in some microprocessors (see register file).
 
-	On a dedicated IC or ASIC (usually in the order of kilobytes).
-	In Field Programmable Gate Array and Complex Programmable Logic Device.
Embedded Use
You can find static RAM in many categories of industrial and scientific subsystems, automotive electronics and similar products. Almost all modern devices, toys and so on that implement electronic user interfaces also embed a certain amount of data (kilobytes or less). Gigabytes can be used for complex products such as digital cameras, mobile phones, synthesizers, etc.
Dual-port SRAM is sometimes used in real-time digital signal processing circuits.
In Computers
SRAM is also used in personal computers, workstations, routers, and peripherals: CPU register files, internal CPU caches, and external burst mode SRAM caches, hard disk buffers, router buffers, etc. LCD screens and printers also typically hold the image displayed (or to be printed) by using static RAM. Some early personal computers (such as ZX80, TRS-80 Model
Hobbyists
Due to the ease of interfacing, hobbyists, especially home-built processor enthusiasts, usually prefer SRAM. Compared to DRAM, it is easier to use because there are no refresh cycles and the address and data buses are directly accessible. In addition to buses and power connections, SRAM typically requires only three controls: Chip Enable (CE), Write Enable (WE) and Output Enable (OE). In synchronous SRAM, Clock (CLK) is also included.
Types of SRAM Memory
+ Non-Volatile SRAM (NV-SRAM)
Non-volatile SRAM (nvSRAM) possesses standard SRAM functionality, but saves data when power is off, thereby ensuring the preservation of critical information. nvSRAM is widely used in many occasions such as networking, aerospace and medical, where the preservation of data is very important and where the battery is impractical.
+ Pseudo SRAM (P-SRAM)
PSRAM features a DRAM memory core and incorporates a self-refresh circuit. They appear externally as a slower SRAM. Compared to true SRAM, they have density/cost advantages without the access complexity of DRAM.
States of SRAM
SRAM cells have three different states: standby (the circuit is in idle state), read (data requested) or write (update content). SRAM operating in read mode and write mode should have “readability” and “write stability”, respectively.
 
III.	SPECIFICATION
In the process of optimizing the performance of SRAM, the careful selection of threshold voltage and frequency plays a pivotal role in ensuring stability and efficiency in static random-access memory. However, to ensure that our designs operate flexibly in various environmental conditions, we also integrate technical specifications related to temperature into the design process.
We carefully choose the threshold voltage to achieve stability in the operation of SRAM. This includes optimizing the threshold voltage not only to control standby current but also to maintain the stability of the cell under various operating conditions.
Moreover, the operating frequency not only influences the data access speed and latency of SRAM but is also closely related to the threshold voltage. To ensure synchronization between performance and energy consumption, we pay special attention to this interaction. Thus, we not only ensure stable performance under specific threshold voltage and frequency settings but also consider the impact of temperature to ensure the reliability and flexibility of SRAM in various environmental conditions.

IV. I/O
Pre-charge
A precharge system of the divided bit line types for a SRAM (Static Random Access Memory) reduces the active current consumption and bit line peak current by decreasing the number of bit lines to be precharged at any one time during a precharge cycle.
Circuit pre-charge helps align the voltage levels of two bit lines before latching the address. The structure of the Precharge circuit is depicted in the diagram below:
![image](https://github.com/user-attachments/assets/10597ac6-2103-4f88-a41e-a82f59a7470f)
Waveform of Precharge Circuit:
![image](https://github.com/user-attachments/assets/77f6b0e9-ac87-4b10-aec9-5cb15b121ebe)

Write driver
The Write driver circuit is to provide sufficient energy to perform the write operation in the SRAM cell. When a write request is activated, the Write Driver circuit enhances the dynamic energy on the data lines to ensure that the new value can be written to the cell accurately and completely.
This process consists of two main stages:
+ Precharge: Before performing a write, the Write Driver circuit typically needs to precharge, setting the voltage to a certain level (which can be either high or low) to prepare for energy transfer when the write is activated.
+ Drive: When a write request is present, the Write Driver circuit will stimulate and provide sufficient energy to change the state of the SRAM cell, transitioning from holding the old value to the newly requested value.
The structure of the Write driver is depicted in the diagram below:
![image](https://github.com/user-attachments/assets/d2f89cf4-e83a-4428-9889-882b3d732aa1)
Waveform of Write driver:
![image](https://github.com/user-attachments/assets/365dcfe6-c96b-4043-80e0-5aa448fba4e6)

Sense Amplifier
Sense amplifier in SRAM is a switching circuit used to amplify and clarify the read signal from SRAM cells. When a specific SRAM cell is selected for reading, the data from the bitline is transmitted to the sense amplifier to boost the signal level and convert the data from the standby current form into a readable signal. The sense amplifier enhances and clarifies the logic state of the data, playing a crucial role in accelerating the readout process from SRAM cells, ensuring performance, and maintaining accuracy in memory operations.
To read the value in Sram memory cells, an AMPLIFIER circuit is needed to SENSE (sense) the value in the memory cell.
The input of a sense amplifier circuit is the bit lines of the SRAM memory cell column with an output voltage of 0 or 1.
The bitline must be loaded before each read cycle to ensure that the difference between the two bitlines is correct. Ensuring that there is a difference between the two bitlines is important. For example, if bit line 0 is loaded first, the reading circuit is likely to read incorrectly and vice versa.
The structure of the Sense amplifier is depicted in the diagram below:
![image](https://github.com/user-attachments/assets/962f6db3-a868-422e-a7c3-349a6642d7f4)
Waveform of Sense amplifier:
![image](https://github.com/user-attachments/assets/3dc076e6-dfcb-4487-81c2-88c6dbac2308)

SRAM CELL
6T-SRAM
A 6T SRAM cell refers to a type of Static Random-Access Memory (SRAM) cell that consists of six transistors. The 6T-SRAM cell consists of two cross-coupled inverters and two access transistors. SRAM is a type of volatile semiconductor memory that stores binary information as long as power is supplied. The 6T SRAM cell is commonly used in integrated circuits (ICs) such as microprocessors and cache memories.
The structure of the 6T-SRAM is depicted in the diagram below:
![image](https://github.com/user-attachments/assets/d02a4729-3d45-459e-a2d4-8c8874f09f14)
The operating principle of 6T SRAM
-	Initialization (Write Operation):
Initially, the two access transistors (usually NMOS transistors) connecting the storage node (bitline) to the bitlines are turned off, isolating the cell from external influences.
The bitlines are precharged to a certain voltage level.
-	Writing a '0' or '1':
To write a '0' to the cell, the write driver forces one of the bitlines (BL or BLB) to a low voltage while the other is kept high.
This causes one of the pull-up transistors in the cross-coupled latch to conduct, establishing a low voltage at one side of the latch.
The low voltage propagates through the latch due to the feedback provided by the cross- coupled inverters, reinforcing the '0' state.
To write a '1' to the cell, the operation is reversed. The other bitline is pulled low while the opposite is kept high, causing the opposite pull-up transistor to conduct and establish a high voltage in the latch.
 
-	Read Operation:
During a read operation, the access transistors are turned on, allowing the contents of the cell to be read onto the bitlines.
The voltage levels on the bitlines are sensed to determine the stored bit. If the voltage on one bitline is higher than the other, it indicates a '1,' and if the voltage on the other bitline is higher, it indicates a '0.'
-	Storage and Stability:
The cross-coupled inverters store the binary state (0 or 1) by maintaining a stable voltage difference between them.
The latch will retain its state until a write operation is performed, or power is removed.
The two access transistors are used to read and write data to the cell. When a read operation is performed, the bit line is precharged to a high voltage level. If the cell contains a logic high, the bit line is discharged through the access transistor, causing a voltage drop. This voltage drop is detected by a sense amplifier, which amplifies the signal and outputs the data1. During a write operation, the bit line is driven to the desired voltage level, and the access transistor is turned on to write the data to the cell1.

Waveform of 6T-SRAM
![image](https://github.com/user-attachments/assets/331c1875-c0a6-4115-86f9-68849c3db675)

4T-SRAM
A 4T SRAM (Static Random-Access Memory) cell is an alternative design to the more commonly used 6T SRAM cell. As the name suggests, the 4T SRAM cell consists of four transistors. It sacrifices some of the stability of the 6T SRAM cell in favor of reduced size and power consumption.
The structure of the 4T-SRAM is depicted in the diagram below:
![image](https://github.com/user-attachments/assets/e09d443b-54cc-4eb5-84e7-a35a21f8c009)
The operating principle of 4T SRAM
Access transistors (2 transistors): These transistors are responsible for connecting the storage node (bitline) to the internal nodes of the cell during read and write operations. They control the access to the memory cell.
Cross-coupled inverters (2 transistors): These transistors form a latch that stores the binary information. The cross-coupled inverters function similarly to the ones in the 6T SRAM cell but with one pair of pull-up/pull-down transistors instead of two pairs.
Write Operation:
During a write operation, the access transistors are turned on, connecting the storage node to the bitlines.
The values to be written are then driven onto the internal nodes of the cell.
Read Operation:
During a read operation, the access transistors are turned on, connecting the storage node to the bitlines.
The voltage on the bitlines is then sensed to determine the stored bit. If one bitline has a higher voltage than the other, it indicates a '1,' and vice versa.
Waveform of 4T-SRAM
![image](https://github.com/user-attachments/assets/0c72f2e2-8289-48b1-a86f-6c479a5ac069)

8T-SRAM
To improve the SRAM cell functionality, several solutions have been proposed from device to architecture level. For instance, the use of new devices such as FinFETs leads to a significant performance improvement. At the cell level, new cells such as 7T, 8T, 9T, 10T, and 11T have been proposed with the focus on improving read static noise margin (RSNM) or write margin (WM). At the architecture level, proposed read and write assist techniques in literature can improve SRAM robustness and performance while occupying less area compared to the cell techniques (e.g. 8T and 10T) and can be used with any type of SRAM. To understand the existing challenges in SRAM design let us explain the operation of standard 6T-SRAM cells.
To overcome this issue, different cell techniques such as 8T-SRAM cell ameliorates the degraded robustness of the standard 6T-SRAM cell by separating read and write bitlines leading to a significant improvement in read static noise margin (RSNM) while the write margin is not affected. The standard 8T-SRAM as it is seen, read and write cycles use different wordlines and bitlines.
![image](https://github.com/user-attachments/assets/50b920a8-8494-40c3-9379-63f1d6044ff4)
The operating principle of 8T SRAM
The basic design of 8T is based on the standard SRAM design with a 6-transistor memory cell. In this design, the 8T separates the two parts of writing and reading data into the SRAM cell, as illustrated by the dashed circle in Figure 4. The transistors AC0 and AC1 are controlled by the write wordline signal (WWL), while AC2 is controlled by the read wordline signal (RWL). The write bitlines (WBT) and write bitline bar (WBB) are used to write data into the SRAM cell. On the other hand, the read bitline signal (RBT) is used to read data from the SRAM cell.
The advantage of separating the write and read parts in the 8T design significantly improves the Read Static Noise Margin (SNM) without affecting the write operation or previously stored data in the memory cell. Compared to the 6T design, the new design is considered asymmetric because it only uses the RBT line to read data. During the read operation, the RBT line is first pulled up to the VDD voltage level. Then, depending on the stored bit value in the memory cell, the RBT line will be pulled down to 0 or remain in the high state.
The structure of the 8T-SRAM is depicted in the diagram below:
![image](https://github.com/user-attachments/assets/cf55ffb0-eb5a-4ff8-9f72-7099196acf53)
Waveform of 8T-SRAM cell
![image](https://github.com/user-attachments/assets/8b7f2e7e-acee-4c5e-84f2-7c21ac7ff3cd)

LP 6T-SRAM
![image](https://github.com/user-attachments/assets/e8064ad9-58f3-480e-bb0c-a49f90efbdb0)

32-BIT SRAM

32-bit 6T-SRAM
![image](https://github.com/user-attachments/assets/1766e304-3959-4da6-adb1-a4fe4d552d4c)
Waveform of the 32-bit 6T-SRAM:
![image](https://github.com/user-attachments/assets/62a72ca8-1d63-4fe2-8c8d-315820cc2bea)

32-bit 4T-SRAM
![image](https://github.com/user-attachments/assets/094a5857-dfdc-42f1-83c6-6a8dbacf40cf)
Waveform of the 32-bit 4T-SRAM:
![image](https://github.com/user-attachments/assets/32787f56-4a8a-4d83-9817-9e8218c2cf62)

32-bit 8T-SRAM
![image](https://github.com/user-attachments/assets/3469f159-554c-4f40-9dec-72f1b3608132)
Waveform of the 32-bit 8T-SRAM 
![image](https://github.com/user-attachments/assets/a7017884-a27a-46a8-b486-2189fa2b6e22)

LP 6T-SRAM
![image](https://github.com/user-attachments/assets/7dbac9f3-0664-454f-8360-417651662fa7)


V.	THE MEASUREMENT RESULTS AND COMPARISONS.
![image](https://github.com/user-attachments/assets/eb7afa79-237e-4e37-bd89-bf73e339fc5a)

Power of I/O
![image](https://github.com/user-attachments/assets/c83d789a-41c2-4146-bee4-c737ddda11d8)
![image](https://github.com/user-attachments/assets/87bbc2cd-0cb5-44b3-922a-123e38aaa70a)

Delay of SRAM cell: 
Table 8: SRAM cells Delay
![image](https://github.com/user-attachments/assets/f6dc8e5c-99fd-4620-b5a3-31f095edbd8e)

Table 9: Voltage supply, Frequencies and power of SRAM cells
![image](https://github.com/user-attachments/assets/018dd718-c16b-4735-8f94-49d9f711290a)
![image](https://github.com/user-attachments/assets/862e2eec-67e5-4c71-8c25-0d0faf3bf163)

Table 10: Voltage supply, Frequencies and power of 32-bit SRAMs
![image](https://github.com/user-attachments/assets/9ca3d514-a9d0-4a6d-a780-4bb78631c407)
![image](https://github.com/user-attachments/assets/8dd94525-5d69-453b-89dc-2ca6c5bca9b3)

Summary:
In summary, the overall power consumption of the 8T design is optimized compared to the 6T design due to the separate write/read path structure.The separate read and write paths in 8T SRAM, while potentially increasing design area, offer advantages in terms of SNM and stability during read operations.
Despite the larger design area, the optimized SNM and reduced susceptibility to noise in 8T SRAM can result in more efficient power utilization compared to 6T SRAM, especially in scenarios where noise considerations and stability are critical.
The overall power efficiency of 8T SRAM, taking into account SNM and design area trade-offs, can make it a favorable choice in applications prioritizing stability and reliability over a smaller footprint.
5.3.	Comparison of power and delay between 6T-SRAM and LP 6T-SRAM.
As in Table 8, we can observe a significant difference in power consumption between 6T- SRAM and LP (Low-Power) 6T-SRAM. This discrepancy lies in their designs.
For LP 6T-SRAM, we employed power gating techniques with the aim of substantially reducing energy consumption during idle states. However, in terms of performance, LP 6T- SRAM may have lower efficiency compared to 6T-SRAM due to potential delays introduced by the activation and deactivation of power gating.
In the case of 6T-SRAM, it excels in high-performance operations for reading and writing data. Nevertheless, given the contemporary demand for low power consumption in devices, the substantial energy consumption during both active and idle states can pose a significant obstacle to meeting user requirements.
Summary:
In the context of increasing demands for both performance and energy efficiency, the comparison between LP (Low-Power) 6T-SRAM and 6T-SRAM becomes crucial. Upon examining Table 8, a notable difference in power consumption between these two SRAM types is evident.
LP 6T-SRAM is designed with the primary goal of reducing energy consumption, especially during idle states, through the use of power gating techniques. Despite potential delays associated with activating and deactivating this technique, LP 6T-SRAM remains a reliable choice for applications prioritizing energy efficiency.
However, 6T-SRAM maintains its advantage with high operational performance. Its ability to meet speed and performance requirements makes it a preferred choice for applications demanding robustness and flexibility.
By utilizing power gating and similar methods, we can develop devices with low power consumption while ensuring stable performance, presenting an opportunity to address diverse user needs in the future.
