# Ex.No.1 — FTK Imager: Forensic Imaging Tool Overview

# Aim

To acquire and preserve digital evidence by capturing both volatile memory (RAM) and non-volatile memory (disk image) using FTK Imager, ensuring data integrity through hash verification for further forensic analysis.


---

## Volatile Memory (RAM)

Steps to capture RAM using FTK Imager:

### Step 1: Run as Administrator
- Open **FTK Imager** with administrative privileges.  
- Right-click the icon → **Run as administrator**  
   **Tip:** Always run as admin to avoid permission issues.

<img src="https://github.com/user-attachments/assets/739f9871-3976-41c3-be50-b8a8da805b63" alt="FTK Imager Memory Capture" width="600">

---

### Step 2: Initiate Memory Capture
- Click **File → Capture Memory...**

<img width="600" alt="ftk1" src="https://github.com/user-attachments/assets/e264b657-58d9-478a-a464-25f5aacb8b18" />


---

### Step 3: Configure Destination
- **Destination Path:** Use an external drive.  
- **Destination Filename:** Default or descriptive name.  
- **Include pagefile.sys:** Optional but recommended.  
- **Create AD1 file:** Optional container.


<img width="600" alt="ftk2" src="https://github.com/user-attachments/assets/9c49d359-253d-43e4-bfaa-46cc8056d574" />


---

### Step 4: Start Capture
- Click **Capture Memory** button to start.  
- Progress depends on RAM size.

<img width="600" alt="ftk4" src="https://github.com/user-attachments/assets/61c5dce1-a434-4457-bea9-ac5fef54b463" />


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

<img width="600" alt="ftk6" src="https://github.com/user-attachments/assets/7fbd0f1b-802e-4348-8f70-c8bb8347165a" />


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

<img width="600" alt="ftk5" src="https://github.com/user-attachments/assets/dba8ef2c-2fdd-41c0-b2e5-e913b09d6a6e" />


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


<img width="600" alt="ftk7" src="https://github.com/user-attachments/assets/d0217634-fc9e-4695-8f2e-30dff1dff6c2" />


---

### Step 5: Start Imaging
- Click **Finish**, check **Verify images after creation**, click **Start**  
- Time depends on drive size.

<img width="600" alt="ftk8" src="https://github.com/user-attachments/assets/7f094962-0ff4-4b4e-836f-68fe47732ace" />


---

### Step 6: Completion and Hash Verification
- FTK Imager shows **MD5** and **SHA1** for source & image  
- Matching hashes confirm integrity.
<img src="https://github.com/user-attachments/assets/739045f1-11bc-474a-9343-2e9aa19ec376" alt="Disk Imaging Animation" width="600">

---

## Result

- Successfully captured **volatile memory (RAM)** using **FTK Imager** and stored the memory dump (`.mem` file) in the specified destination folder.  
- Successfully created a **non-volatile memory (disk) image** of the target drive in **E01 (EnCase)** format.  
- **MD5** and **SHA1 hash values** of the source and image matched, confirming **data integrity** and authenticity of the acquired evidence.  
- The captured images can now be analyzed using forensic tools like **Autopsy**, **FTK Toolkit**, or **Volatility** for further investigation.
