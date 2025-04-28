# External SSD Setup Guide for VM Labs

## Project Goal

This document outlines the research, decision making process and setup for selecting an external SSD and USB enclosure to host virtual machines. The goal was to find a cost effective solution that delivers reliable performance for running VM based labs — both to overcome internal storage limitations and to showcase my technical skills for IT related apprenticeships or entry level roles.

## The Challenge

My primary PC has limited internal storage and the USB ports are **3.2 Gen 1**, which has a maximum theoretical throughput of **5Gbps** (approximately 500-600 MB/s real-world). This bottleneck limits the performance of external NVMe SSDs, making it essential to balance performance, thermals, compatibility and cost when selecting components.

## Final Selected Components

*   **SSD:** WD_BLACK SN770 NVMe SSD - 1TB
*   **Enclosure:** SSK Aluminum M.2 NVMe/SATA SSD Enclosure (Model SHE-C325PRO, RTL9210B Chipset)

This pairing offers solid performance, good thermal handling and USB/UASP compatibility at a reasonable price, ideal for lab workloads involving virtualisation and frequent disk access.

## Guide Contents

*   **[SSD Selection Process](./SSDS.md):** Evaluation of various Gen4 NVMe SSDs, their performance specs, DRAM presence, TBW ratings and thermal profiles.
*   **[USB Enclosure Selection Process](./usb-enclosure-guide.md):** Analysis of enclosure chipsets, heat dissipation and UASP support.
*   **[Benchmark Results](./benchmark-results.md):** Performance testing with tools like AS SSD and Windows PowerShell disk speed tests.

## Why This Project Matters
Having fast, portable external storage is crucial for VM labs, especially in cybersecurity. Disk I/O bottlenecks can severely impact system performance during malware analysis, packet capture, or multitiered lab simulations. This project reflects a practical application of hardware knowledge, benchmarking, system limitations and optimisation under constraints.

## Future Improvements
- Exploring cooling options (passive and active) for better thermal management.
- Testing with USB 3.2 Gen 2 interfaces and Thunderbolt enclosures.
- Comparing performance in live VM usage scenarios (e.g., Kali Linux, Windows Server, Metasploitable).
