

#   Ex.No.3   Wireshark – Network Packet Capture and Analysis Tool<br>

# 🌐 Website Used: [http://demo.testfire.net/](http://demo.testfire.net/)
## Procedure: Capturing Plaintext Passwords

### Step 1: Start Capturing Packets

- First, open Wireshark. You will see a list of all available network interfaces (e.g., "Wi-Fi," "Ethernet").

- Select the interface your computer is using to connect to the internet (in this case, Wi-Fi).

  <p align="center">
<img width="955" height="1014" alt="wir1" src="https://github.com/user-attachments/assets/5575724f-63de-43f4-837a-e531e1c8ae47" />

  </p>

- Click the blue shark fin icon 🦈 in the top-left corner to start the capture. Wireshark will immediately begin capturing all traffic passing through that interface.

  <p align="center">
  <img width="951" height="908" alt="wir4" src="https://github.com/user-attachments/assets/024e4e8a-114f-4763-8b93-1ac52f366260" />

 </p>

---

### Step 2: Generate Login Traffic

- Open a web browser and navigate to **http://demo.testfire.net/**

- Enter any dummy credentials. For this example, we'll use:

   Username: testuser  
   Password: password123  

- Click the login button. The login will fail, but the data has already been sent across the network.

  <p align="center">
<img width="1893" height="886" alt="wir2" src="https://github.com/user-attachments/assets/113dfb32-aa7d-4928-bacd-9e5f4964d479" />

 </p>

---

### Step 3: Stop Capture and Filter Traffic

- Return to Wireshark and click the Stop button (the red square).

- In the display filter bar, you need to find the packet containing the login data. Since the form data was sent to the server, we will look for an HTTP POST request.

- Apply the following filter to find the exact packet and press Enter:

  <p align="center">
<img width="954" height="304" alt="wir6" src="https://github.com/user-attachments/assets/cb0d3a05-8285-4f98-8c67-0bf8f402ded0" />

 </p>

---

### Step 4: Inspect the Packet to Find Credentials 

- In the filtered packet list, you should see a packet with information like "POST /userinfo.php". Select this packet.

- In the Packet Details pane below the list, expand the following sections:

  - Hypertext Transfer Protocol  
  - HTML Form URL Encoded  

- Inside the "HTML Form URL Encoded" section, you will see the credentials you entered in plaintext.

  <p align="center">
  <img width="870" height="624" alt="wir3" src="https://github.com/user-attachments/assets/0ac2527b-5fbf-4b10-bbc3-c230c3147777" />

 </p>

---

## ✅ Result

The experiment successfully intercepts the login credentials in a human-readable format. The analysis of the captured POST packet reveals the plaintext data that was transmitted over the network.

This result confirms the inherent security flaw of the **HTTP protocol**:  
- Any sensitive data sent over HTTP is transmitted openly.  
- It is trivial to intercept by an attacker.  
