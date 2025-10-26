## 🕵️ Ex.No.9: Analyzing Suspicious Processes with Process Explorer 🖥️

**Overview**  
**Process Explorer** is a powerful Windows tool that provides detailed insights into running processes. It helps monitor system activity, troubleshoot issues, and detect potentially malicious or unusual processes. 🔍

---

### Step 1: Download and Launch Process Explorer ⬇️

* **Get Process Explorer:**  
  Visit the Microsoft Sysinternals website and download the tool. 🌐
* **Extract Files:**  
  Unzip the downloaded package into a dedicated folder. 📂
* **Run as Administrator:**  
  Open the folder and launch `procexp64.exe` or `procexp.exe` by right-clicking and selecting **Run as Administrator**. 🛡️

<img width="1388" alt="Compilation Screenshot" src="../assets/exp9.1.png" />
---

### Step 2: Explore the Interface 🖱️

Process Explorer displays processes in a hierarchical tree structure. Each process is **color-coded** based on its status:

| Color | Description |
| :--- | :--- |
| **Pink** | Suspended processes ⏸️ |
| **Light Blue** | Processes running under your account 👤 |
| **Dark Blue** | System services or processes 🖥️ |
| **Green** | Newly started processes 🟢 |
| **Red** | Recently terminated processes ❌ |

---

### Step 3: Spotting Suspicious Processes ⚠️

To investigate potentially harmful processes:

1. **Check Unknown Processes:**  
   Look for unfamiliar names. Trusted processes usually come from known vendors like Microsoft, Adobe, or Intel. ✅
2. **Verify Digital Signatures:**  
   Right-click → **Properties** → **Image** tab. Check for a valid **Digital Signature**. Unsigned processes may be risky. 🛑
3. **Examine File Paths:**  
   Check the **Path** under the Image tab. Legitimate system processes are usually in `C:\Windows\System32`. Running from temp or user folders is suspicious. 📁
4. **Monitor Resource Usage:**  
   Watch for processes consuming excessive CPU, memory, or disk resources without explanation. 💻
5. **Review Process Details:**  
   Lack of description or unclear company names can indicate a suspicious process. 🕵️‍♂️
6. **Inspect Network Activity:**  
   Right-click → **Properties** → **TCP/IP** tab. Unexpected external connections require attention. 🌐

---
<img width="1388" alt="Compilation Screenshot" src="../assets/exp9.2.png" />

### Step 4: Research Suspicious Processes 🔎

* Search the process name online (e.g., `cmd.exe`) to learn more about it. 🌍  
* Use databases like **VirusTotal** or **ProcessLibrary** to check for known malware. 🦠


<img width="1388" alt="Compilation Screenshot" src="../assets/exp9.3.png" />
---

### Step 5: Handle Malicious or Unwanted Processes 🛠️

* **Terminate:** Right-click → **Kill Process** to stop it immediately. ❌  
* **Suspend:** Right-click → **Suspend** to pause execution temporarily. ⏸️  
* **Delete Source:** Locate the executable via its Path and remove it if confirmed malicious. 🗑️

---
<img width="1388" alt="Compilation Screenshot" src="../assets/exp9.4.png" />
---

### Step 6: Conduct a Full System Scan 🧹

* Run a comprehensive antivirus scan. 🛡️  
* Use malware removal tools (e.g., Malwarebytes or Windows Defender) for a thorough cleanup. 🧰
