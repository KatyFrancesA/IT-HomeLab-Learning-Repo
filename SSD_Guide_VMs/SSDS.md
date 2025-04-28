# NVMe SSD Selection Process

## Goal
To select a 1TB M.2 NVMe SSD suitable for running virtual machines externally via USB, prioritising responsiveness (IOPS), TBW and value for money, while acknowledging the USB 3.2 Gen 1 (5Gbps) bottleneck on my PC.

## Key Requirements

*   Interface: M.2 NVMe (PCIe)
*   Capacity: 1TB
*   Performance: Good Random Read/Write IOPS
*   TBW: 600+
*   Compatibility: Standard 2280 form factor
*   Budget: < £70

**TBW:** A minimum TBW (Terabytes Written) rating of 600TB was targeted to ensure long term endurance and reliability for the write intensive operations often associated with installing, running and modifying virtual machines over several years.  
<br /> 
**IOPS:** Prioritised drives with strong Random Read/Write IOPS (Input/Output Operations Per Second), particularly at low queue depths (QD1), as this heavily influences perceived system responsiveness, OS boot times and application loading speeds within the virtual machine environments, which is more critical for this use case than peak sequential speed limited by the USB interface.  
<br /> 
**Internal IOPS Comparison:** The target external drive's IOPS were compared against the benchmarked performance of the internal system drive (15.5K Read / 31K Write QD1 IOPS) to ensure a noticeable improvement in VM responsiveness.  

## Options Considered

1. **Samsung 980 Pro (1TB, With Heatsink)** - £60    
**Model Number:** MZ-V8P1T0CW   
**Interface:** PCIe Gen 4.0 x4, NVMe 1.3c  
**DRAM:** Yes 1GB  
**Form Factor:** 2280  
**Sequential Read/Write:** 7,000 / 5,000 MB/s  
**Random Read/Write IOPS:**  
QD1, T1: 22K / 60K  
QD32, T16: 1M / 1M   
**TBW:** 600    
**Power Consumption:** 6.2W active   
**Controller:** Samsung in-house Controller  
**NAND:** Samsung V-NAND 3bit MLC   
**Operating Temp:** 0 - 70°C   
**System Compatibility:** Desktops and laptops meeting PCI-SIG D8 specs     
**Encryption Support:** AES 256-bit Encryption (Class 0), TCG/Opal, IEEE1667   
**Warranty:** 5 year (Limited)   

- ***Pros:*** Excellent performance, DRAM aids consistency under heavy workloads, reasonable price for the heatsink version.  
- ***Cons:*** Doesn't fit standard enclosures and non heatsink version is out of budget, making the DRAM benefit poor value given the USB bottleneck.  
- ***Status:*** Eliminated due to enclosure compatibility challenges.  

<br /> 

2. **WD Black SN770 (1TB)** - £58  
**Model Number:** WDS100T3X0E-00B3N0  
**Interface:** PCIe® Gen4 16GT/s  
**DRAM:** No (HMB)  
**Form Factor:** 2280   
**Sequential Read/Write:** 5,150 / 4,900 MB/s   
**Random Read/Write IOPS:** 740K / 800K   
**Estimated QD1/T1 IOPS:** 70K / 100K - (based on [KitGuru review](https://www.kitguru.net/components/ssd-drives/simon-crisp/wd-black-sn770-1tb-ssd-review/all/1/?utm_source=chatgpt.com))   
**TBW:** 600   
**Power Consumption:** 5.3W active   
**Controller:** SanDisk proprietary  
**NAND:** SanDisk TLC (BiCS5)  
**Operating Temp:** 0 to 85°C    
**System Compatibility:** Backward-Compatible with PCIe Gen3 x4, PCIe Gen3 x2, PCIe Gen3 x1, PCIe Gen2 x4, PCIe Gen2 x2 and PCIe Gen2 x1, Windows 8.1, 10, 11   
**Encryption Support:** No   
**Warranty:** 5 year (Limited)   

- ***Pros:*** Excellent IOPS for a DRAM-less drive. Known for high power efficiency and running relatively cool, making it well-suited for enclosures.   
- ***Cons:***  Slightly more expensive than Kioxia G3, but offers better QD1 performance.  
- ***Status:*** Selected.  
  
<br /> 

3. **WD Black SN7100 (1TB)** - £60   
**Model Number:** WDS100T4X0E-00CJA0    
**Interface:** PCIe Gen 4 x4   
**DRAM:** No (HMB)   
**Form Factor:** 2280   
**Sequential Read/Write:** 7,250 / 6,900 MB/s   
**Random Read/Write IOPS:** 1M / 1.4M   
**Estimated QD1/T1 IOPS:** 70K / 100K (inferred)   
**TBW:** 600   
**Power Consumption:** 4.5 W active   
**Controller:** Western Digital Polaris 3 (A101-000172-A1)   
**NAND:** Sandisk 218-Layer TLC (BiCS8)   
**Operating Temp:** 0 - 85°C   
**System Compatibility:** Backwards compatible with PCIe Gen4 x2, PCIe Gen4 x1, PCIe Gen3 x4, PCIe Gen3 x2, PCIe Gen3 x1, PCIe Gen2 x4, PCIe Gen2 x2 and PCIe Gen2 x1, Windows 10+  
**Encryption Support:** AES 256-bit Encryption  
**Warranty:** 5 year (Limited)   

- ***Pros:*** Top-tier peak performance specs.   
- ***Cons:*** Sequential speed advantage irrelevant due to USB bottleneck. Thermal concerns with the SN7100 make it unsuitable for passive USB enclosures.  
- ***Status:*** Eliminated due to thermal concerns and poor value over USB.  

<br /> 

4.  **Kioxia Exceria Plus G3 (1TB)**  - £46  
**Model Number:** LSD10Z001TG8      
**Interface:** PCI Express Base Specification Revision 4.0 (PCIe)   
**DRAM:** No (HMB)    
**Form Factor:** 2280   
**Sequential Read/Write:** 5,000 / 3,900 MB/s   
**Random Read/Write IOPS:** 770K / 950K  
**Estimated QD1/T1 IOPS:** 17K / 57K - (based on [SSD Tester ](https://ssd-tester.com/kioxia_exceria_plus_g3_1tb.html))  
**TBW:** 600   
**Power Consumption:** 5.3W active   
**Controller:** Phison PS5021-E21T   
**NAND:** BiCS FLASH TLC   
**Operating Temp:** 0 - 85°C   
**System Compatibility:** Compatible with PCI Express Base Specification Revision 4.0 and NVM Express Revision 1.4 command set    
**Encryption Support**: AES 256-bit Encryption    
**Warranty:** 5 year (Limited)   

- ***Pros:*** Best price. Performance metrics very close to SN770. Fits standard enclosures.  
- ***Cons:*** Brand slightly less mainstream than WD/Samsung (though Kioxia is Toshiba Memory's successor - reputable).   
- ***Status:*** Eliminated due to lower QD1 random read performance compared to the SN770 for a small price difference.  

## Reasoning for Final Choice (WD Black SN770)

The primary goal was responsive external storage for virtual machines within a budget and considering a 5Gbps USB bottleneck.  

The Samsung 980 Pro was initially appealing due to its DRAM cache. However, the heatsink version presented enclosure compatibility issues and the non heatsink version was over double the price making it far above my budget and the performance gains poor value over the limited USB connection.  

The SN7100 had impressive peak specs but the benchmarks showed it ran too hot for my needs and would've needed active cooling to prevent thermal throttling, which made it a poor fit for USB enclosures, especially considering most of its performance edge would be strangled by the USB connection anyway.  

The final decision came down to the WD Black SN770 and the Kioxia Exceria Plus G3. While the Kioxia offered the lowest price, the SN770 demonstrated significantly higher low-queue-depth (QD1) random read performance (70K IOPS vs 17K IOPS) based on third-party benchmarks. This specific metric heavily influences perceived system responsiveness, OS boot times and application loading within VMs. Given the small price difference of £9 the potential improvement in VM user experience offered by the SN770's superior QD1 read speeds justified the slightly higher cost. I must address the fact the SN770 doesn't have built in encryption but I always planned on implementing software based encryption on whatever SSD I chose due to potential vulnerabilities associated with flawed firmware implementations of hardware encryption (like the TCG Opal bypass issues found in the past).  

Therefore the **WD Black SN770 was selected** as it provided the best balance of price crucial low queue depth random read performance thermal efficiency and standard enclosure compatibility for this specific use case. Setting aside budget and interface limitations the ideal choice might have been the Samsung 980 Pro without the heatsink but the SN770 represents the optimal practical solution under the existing constraints.  

## Why Performance Still Matters Over USB  

Although my PC could potentially handle running a couple of VMs directly using internal storage I decided to go for the SSD in USB enclosure for the following reasons:  

- **Separation:** Keeps your VM environment separate from your main OS drive.
- **Performance:** Leverages the high random I/O performance of an NVMe SSD. Even with the USB bottleneck limiting sequential speeds, this provides a significantly better experience for running VMs (faster OS boot, quicker application loading) compared to slower storage options like SATA SSDs or HDDs.  
- **Offloading:** Running VMs is I/O intensive; putting this load on a separate drive reduces I/O contention on internal storage, making the host OS feel more responsive while VMs are active.  

While USB 3.2 Gen 1 severely limits sequential read/write speeds, it does not bottleneck IOPS as drastically, the USB port will add latency and reduce the IOPS from its native potential, but the SN770's external IOPS are still significantly higher than my internal drive's
(15.5K/31K), a high-IOPS NVMe drive in a USB enclosure will still feel much snappier for running VMs than a slower SATA SSD or a mechanical hard drive connected via the same USB port.

