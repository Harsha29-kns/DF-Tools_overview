# Ex.No.1 — FTK Imager: Forensic Imaging Tool Overview

![FTK Imager](https://img.shields.io/badge/FTK_Imager-4.5-blue)

---

## Table of Contents
- [Volatile Memory (RAM)](#volatile-memory-ram)
- [Non-Volatile Memory (Disk Image)](#non-volatile-memory-disk-image)
- [Notes](#notes)
- [References](#references)

---

## Volatile Memory (RAM)

Steps to capture RAM using FTK Imager:

### Step 1: Run as Administrator
- Open **FTK Imager** with administrative privileges.  
- Right-click the icon → **Run as administrator**  
📁 **Tip:** Always run as admin to avoid permission issues.

<img src="https://github.com/user-attachments/assets/739f9871-3976-41c3-be50-b8a8da805b63" alt="FTK Imager Memory Capture" width="600">

---

### Step 2: Initiate Memory Capture
- Click **File → Capture Memory...**

<img src="../assets/ftk1.png" alt="FTK Imager Memory Capture" width="600" alt="Memory Capture Animation" width="600">

---

### Step 3: Configure Destination
- **Destination Path:** Use an external drive.  
- **Destination Filename:** Default or descriptive name.  
- **Include pagefile.sys:** Optional but recommended.  
- **Create AD1 file:** Optional container.

<details>
<summary>View Screenshot</summary>
<img src="../assets/ftk2.png" alt="Memory Destination" width="600">
</details>

---

### Step 4: Start Capture
- Click **Capture Memory** button to start.  
- ⏳ Progress depends on RAM size.

<img src="../assets/ftk4.png" alt="Start Capture Animation" width="600">

---
### 5. Wait for Completion
- A progress bar will indicate the capture status.  
- Capture time depends on the system’s RAM size.  
- Once finished, the memory dump file will be available in the destination folder.
---
<br>

## Non-Volatile Memory (Disk Image)

### Step 1: Start the Process
- Go to **File → Create Disk Image...**  

<img src="../assets/ftk6.png" alt="Create Disk Image" width="600">

---

### Step 2: Select Source Type
| Type | Description |
|------|-------------|
| Physical Drive | Entire disk including partitions, unallocated space, MBR |
| Logical Drive | Specific partition (e.g., C:) |
| Image File | Copy/convert existing image |
| Folder Contents | Only a specific folder |

---

### Step 3: Select Source Drive
- Connect via **write-blocker** → select drive → **Finish**

<img src="../assets/ftk5.png" alt="Select Source" width="600">

---

### Step 4: Configure Destination
- Click **Add...** → choose **Image Type** and **Destination**  

| Image Type | Description |
|------------|-------------|
| E01 | EnCase format, compresses data, includes metadata |
| Raw (DD) | Bit-for-bit copy, no extra features |
| AFF | Open forensic format, supports compression |

- Fill in **Evidence Info**: Case details, examiner name, description.  
- **Image Fragment Size:** Set 0 for single file.

<details>
<summary>View Screenshot</summary>
<img src="../assets/ftk7.png" alt="Disk Destination" width="600">
</details>

---

### Step 5: Start Imaging
- Click **Finish**, check **Verify images after creation**, click **Start**  
- ⏳ Time depends on drive size.

<img src="../assets/ftk8.png" alt="Disk Imaging Animation" width="600">

---

### Step 6: Completion and Hash Verification
- FTK Imager shows **MD5** and **SHA1** for source & image  
- ✅ Matching hashes confirm integrity.
<img src="https://github.com/user-attachments/assets/739045f1-11bc-474a-9343-2e9aa19ec376" alt="Disk Imaging Animation" width="600">
---

## Notes
> ⚠ Always use a **write-blocker**  
> ✅ Hash verification ensures chain-of-custody  
> 📁 Image fragmentation helps with large drives  

---

## References
- [FTK Imager Official Website](https://accessdata.com/product-download/ftk-imager-version-4-5)  
- FTK Imager Documentation
