# External SSD Setup Guide for VM Labs

## Project Goal

This document outlines the research, decision-making process and setup for selecting an external SSD and USB enclosure to host virtual machines for my planned projects. The primary goal was to find a cost effective solution providing good performance for running VMs, overcoming internal storage limitations.

## The Challenge

My primary PC has limited internal storage space available. Furthermore, the available external connection is a **USB 3.2 Gen 1 port**, which has a maximum theoretical throughput of **5Gbps** (approximately 500-600 MB/s real-world). This USB bottleneck significantly impacts the maximum sequential read/write speeds achievable from high-performance NVMe drives when used externally.

## Final Selected Components

*   **SSD:** Kioxia Exceria Plus G3 1TB NVMe M.2 SSD
*   **Enclosure:** SSK Aluminum M.2 NVMe/SATA SSD Enclosure (Model SHE-C325, RTL9210B Chipset)

## Guide Contents

*   **[SSD Selection Process](./SSDS.md):** Details on the NVMe drives considered and the reasoning for the final choice.
*   **[USB Enclosure Selection Process](./usb-enclosure-guide.md):** Details on the USB enclosures evaluated and the final choice.
*   **[Benchmark Results](./benchmark-results.md):** Performance benchmarks of the internal drive and the external SSD setup.
