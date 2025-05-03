# Initial SSD Setup and Formatting

After physically installing the WD Black SN770 M.2 SSD into the SSK SHE-C325 enclosure and connecting it to my PC via USB the drive required initialisation and formatting before use.

## Partitioning and Formatting Process

The following steps were taken using Windows Disk Management:

1.  **Open Disk Management:** Accessed via the Power User menu (Win + X) and selecting 'Disk Management'.
2.  **Identify New Disk:** Located the new 1TB disk in the lower pane, initially showing as 'Unknown' with 'Unallocated' space.
3.  **Initialise Disk:**
    *   Right clicked the disk area on the left and selected 'Initialize Disk'.
    *   Chose the **GPT (GUID Partition Table)** partition style *- GPT is the modern standard supporting large drives and more partitions than the older MBR.*
    *   Clicked OK. The disk status changed to 'Online'.
4.  **Create New Volume:**
    *   Right clicked the 'Unallocated' space for the disk.
    *   Selected 'New Simple Volume...'
    *   **Followed the wizard:**
        *   **Size:** Accepted the default maximum size to use the entire disk capacity for a single partition, simplifying management for VM storage.
        *   **Drive Letter:** Assigned an available drive letter.
        *   **Format:**
            *   **File System:** **NTFS** was chosen.
                *   *Reasoning:* NTFS provides robustness through **journaling** (protecting against data corruption from unexpected shutdowns) supports large files needed for VMs and offers features like permissions. It has excellent read/write compatibility with modern Linux distributions (via `ntfs-3g`) commonly used in VMs alongside native Windows support. While exFAT offers cross platform compatibility it lacks journaling making it not the best choice for active VMs.
            *   **Allocation Unit Size:** Default was selected as it provides a good balance for storing large VM disk files and smaller OS files within VMs.
            *   **Volume Label:** Assigned 'External SSD'.
            *   **Quick Format:** Enabled for speed.
            *   **NTFS Compression:** Default file/folder compression was **left disabled** during format to avoid potential performance overhead on active VM disk I/O. Compression can be enabled later on specific folders if needed.
        *   Clicked Finish.
5.  **Verification:** After formatting completed the drive appeared in File Explorer with the assigned letter and label ready for use.

## Veracrypt Full Disk Encryption

For enhanced data security especially when working with potentially sensitive lab environments or tools I encrypted the entire external SSD partition using Veracrypt.

1.  **PGP Signature Verification:** Before installation the downloaded Veracrypt installer's authenticity was verified against its PGP signature using Gpg4win (Kleopatra).
    *   *Steps:* Downloaded the Veracrypt installer (`.exe`) the corresponding signature file (`.sig`) and the Veracrypt public PGP key (`.asc`). Imported the public key into Kleopatra. Used Kleopatra's 'Decrypt/Verify' function selecting the `.sig` file which then automatically checked it against the `.exe` file confirming a 'Good signature'.
2.  **Volume Creation:**
    *   Launched Veracrypt and selected 'Create Volume'
    *   Chose 'Encrypt a non-system partition/drive'
    *   Selected 'Standard Veracrypt volume'
    *   Selected the target device corresponding to the external SSD
    *   Chose '**Create encrypted volume and format it**' (recommended for new/empty drives)
3.  **Encryption Settings:**
    *   Encryption Algorithm: **AES** (default - secure and hardware-accelerated)
    *   Hash Algorithm: **BLAKE2s** (default in recent versions - secure and fast)
4.  **Password/Keyfiles:** A **strong unique passphrase** was generated and securely stored separately. Additionally keyfiles located on a separate secure USB drive were used for enhanced security.
    *   *PIM was left at default for now for optimal balance of security and mount speed.*
5.  **Formatting within Veracrypt:**
    *   Confirmed support for large files (>4GB)
    *   Selected **NTFS** as the filesystem within the encrypted volume
    *   Used **Quick Format**
    *   Generated sufficient random data for the keys by moving the mouse within the window
    *   Confirmed formatting warning and proceeded
6.  **Mounting/Dismounting:** The encrypted volume is mounted by selecting the device in Veracrypt choosing an available drive letter clicking 'Mount' and entering the password (and providing keyfiles). The volume **must be Dismounted** in Veracrypt before physically unplugging the drive to ensure data integrity and security.

*(Note: Hidden volumes were not used for this setup but offer plausible deniability for highly sensitive data.)*