# Cloud C2 Installation Lab (Hak5 Cloud C2 Setup Guide)

## Overview
This lab walks through installing and configuring **Hak5 Cloud C2**, setting it up on a Windows Server 2022 virtual machine, and connecting it to a lab wireless router network for cybersecurity testing.

---

## Learning Objectives
By the end of this lab, you will be able to:
- Install Cloud C2 on a Windows Server VM
- Handle antivirus and firewall restrictions
- Configure VM networking (NAT and Bridged adapters)
- Set up a wireless router for lab use
- Deploy and access Cloud C2 through a web interface
- Verify full network and server functionality

---

## Pre-Install Requirements
- VirtualBox or similar VM software
- Windows Server 2022 installed
- Network adapter set to NAT initially
- Admin access to VM
- Internet connection

---

# Lab Steps

## Step 1: VM Preparation
- Launch Windows Server 2022 VM
- Set network adapter to **NAT**
- Disable Windows Firewall:
  - Windows Defender Firewall → Turn on/off
  - Turn OFF Domain, Private, and Public profiles

---

## Step 2: Download Cloud C2
- Go to:
  https://downloads.hak5.org/cloudc2
- Select version:
  - 3.5.2-stable
- Download ZIP file

---

## Step 3: Handle Windows Defender Block (If Needed)
If download is blocked:
- Open Windows Security
- Go to Virus & threat protection → Protection history
- Find Cloud C2 file
- Click Actions → Allow

---

## Step 4: Extract Files
- Navigate to:
  C:\Users\Administrator\Downloads
- Create folder:
  C:\Users\Administrator\CloudC2
- Extract ZIP into folder
- Confirm file exists:
  c2-3.5.2_amd64_windows.exe

---

## Step 5: Start Cloud C2 Server
Open Command Prompt:
```bash
cd C:\Users\Administrator\CloudC2
c2-3.5.2_amd64_windows.exe -hostname <VM_IP_ADDRESS>
```

- Record the **Setup Token**

---

## Step 6: Web Interface Setup
Open browser:
http://<VM_IP_ADDRESS>:8080

Enter:
- Setup Token
- Product Key (from Hak5 purchase)

Create login:
- Username: Lab@<firstInitial_lastName>
- Password: Passw0rd!

---

## Step 7: Verify Installation
- Log into Cloud C2 dashboard
- Restart Cloud C2 server
- Confirm login still works

---

## Step 8: Wireless Router Setup (Asus RT-N66U)
- Power on router (NOT connected to switch yet)
- Hold RESET for 10 seconds
- Connect laptop via LAN port
- Open:
http://192.168.1.1

Login:
- Username: admin
- Password: Passw0rd!

Configure:
- Mode: Wireless Router Mode
- Internet: No username/password required
- DHCP: Automatic
- SSID: CYBlab<firstInitial_lastName>
- Password: Passw0rd!

---

## Step 9: Configure VM Network Adapters

### Adapter 1
- Bridged Adapter
- Intel Wi-Fi 6E AX211
- Intel PRO/1000 MT Desktop

### Adapter 2
- Bridged Adapter
- Realtek USB GbE Family Controller
- Intel PRO/1000 MT Desktop

---

## Step 10: Set Interface Priority (Metric)

Control Panel → Network and Sharing Center → Change Adapter Settings

Set:
- Internet adapter → Metric 10
- Ethernet adapter → Metric 50

---

## Step 11: Restart and Verify Network
- Restart VM
- Run:
ipconfig
- Confirm router-assigned IP address

---

## Step 12: Restart Cloud C2 with New IP
Run:
c2-3.5.2_amd64_windows.exe -hostname <new_VM_IP_ADDRESS>

Access from any device:
http://<new_VM_IP_ADDRESS>:8080

---

# Lab Verification Checklist
- [ ] Cloud C2 installed successfully
- [ ] Server runs properly
- [ ] Setup token recorded and used
- [ ] Web UI accessible on port 8080
- [ ] Router SSID created
- [ ] VM receives IP address
- [ ] Remote access works

---

# Lab Questions

## Basic Understanding
1. What is Cloud C2 used for?
2. Why disable Windows Defender temporarily?
3. What is the setup token used for?

---

## Networking
4. What is NAT vs Bridged networking?
5. Why does interface metric matter?
6. What IP range did the router assign?

---

## Troubleshooting
7. Why might port 8080 not load?
8. How do you fix a blocked download?
9. Why might DHCP fail in the VM?

---

## Analysis
10. Why isolate a lab network in cybersecurity testing?
11. What is Cloud C2 used for in real-world environments?
12. What risks exist when disabling firewall/antivirus?
