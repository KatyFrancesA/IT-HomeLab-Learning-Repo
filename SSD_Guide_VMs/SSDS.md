# NVMe SSD Selection Process

## Goal

To select a 1TB M.2 NVMe SSD suitable for running virtual machines externally via USB, prioritising responsiveness (IOPS) and value for money, while acknowledging the USB 3.2 Gen 1 (5Gbps) bottleneck.

## Key Requirements

*   Interface: M.2 NVMe (PCIe)
*   Capacity: 1TB
*   Performance: Good Random Read/Write IOPS for VM responsiveness.
*   Compatibility: Standard 2280 form factor (no tall heatsinks preferred for enclosure compatibility).
*   Budget: Aim for best value under £70.

## Options Considered

2.  **Samsung 980 Pro (1TB, With Heatsink)**
         Price: £60
    =   *Specs:* PCIe Gen 4, High IOPS, **DRAM Cache**, **8.6mm height**
    *   *Pros:* Excellent performance, DRAM cache aids consistency under heavy load, reasonable price (for the heatsink version).
    *   *Cons:* oesn't fit standard enclosures and non heatsink out of budget, making the DRAM benefit poor value given the USB bottleneck. 
    *   *Status:* Eliminated due to enclosure compatibility challenges.

2. **WD Black SN770 (1TB)**
    *   *Price:* £55
    *   *Specs:* PCIe Gen 4, High IOPS, DRAM-less, Standard Height.
    *   *Pros:* Excellent IOPS for a DRAM-less drive. Known for high power efficiency and running relatively cool, making it well-suited for enclosures.
    *   *Cons:* Slightly more expensive than Kioxia G3.
    *   *Status:* Strong contender.

3.  **WD Black SN7100 (1TB)**
    *   *Price:* £60
    *   *Specs:* PCIe Gen 4, Very High IOPS/Sequential speeds. SN7100 noted as DRAM-less and potentially needing active cooling.
    *   *Pros:* Top-tier peak performance specs.
    *   *Cons:* Sequential speed advantage irrelevant due to USB bottleneck. SN7100 thermal concerns make it unsuitable for passive USB enclosures. Price higher than SN770/Kioxia.
    *   *Status:* Eliminated due to thermal concerns and poor value over USB.

5.  **Kioxia Exceria Plus G3 (1TB)**
    *   *Price:* £46
    *   *Specs:* PCIe Gen 4, High IOPS (similar to SN770), DRAM-less, Standard Height.
    *   *Pros:* **Best price.** Performance metrics very close to SN770. Fits standard enclosures.
    *   *Cons:* Brand slightly less mainstream than WD/Samsung (though Kioxia is Toshiba Memory's successor - reputable).
    *   *Status:* **Selected.**

## Reasoning for Final Choice (Kioxia Exceria Plus G3)

The USB 3.2 Gen 1 (5Gbps) bottleneck negates the sequential speed advantages of higher-end PCIe Gen 4 drives. Therefore, the focus shifted to good Random IOPS (important for VM responsiveness) and value for money.

Both the WD Black SN770 and Kioxia Exceria Plus G3 offered very similar high IOPS performance for DRAM-less drives. Given the bottleneck, the real-world difference in VM responsiveness between these two was expected to be negligible.

The Kioxia Exceria Plus G3 provided essentially the same relevant performance profile as the SN770 but at a lower price (£46 vs £55). Therefore, the **Kioxia Exceria Plus G3 was chosen as the best value option** for my VM lab setup.
