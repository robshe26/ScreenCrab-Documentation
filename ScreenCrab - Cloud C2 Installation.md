# Cloud C2 Installation Guide

This is a guide on the download and setup of Hak5's Clould C2 software

## Pre-Install Requirements 

- Virtual Box or any Virtual Machine software
- Installation of Windows Server 2022 on the Virtual Machine
- Network adapter set to:
    - Bridged Adapter

## Step 1: Download the software Cloud C2

1. In the Windows Server VM:
- Go to [Hak5] (https://downloads.hak5.org/cloudc2)

___Example pictured here:___
<img width="975" height="734" alt="image" src="https://github.com/user-attachments/assets/3ea00913-11ce-4685-a3c2-a0d812716c74" />

2. Select 3.5.2-stable and begin the download

4. After the download is complete go to Windows File Manager &rarr; Downloads

___Example pictured here:___
<img width="975" height="678" alt="image" src="https://github.com/user-attachments/assets/e7632eff-d5f8-4fed-b6ac-6336a22f6ff8" />

5. Click on the compressed `.zip`  file that is in the Downloads folder in File Explorer
- Click **EXTRACT ALL**
- If this was done correclty you should see `c2-3.4.2_amd64_windows.exe` in /Downloads/c2-3.5.2
<img width="779" height="582" alt="image" src="https://github.com/user-attachments/assets/b7cd612c-d2fd-419b-9cc6-9bbe33482d1a" />

6. Start Commnad Prompt(cmd.exe)
- First change the Directory to the Directory with the Server File:
- cd downloads/<filename>
- Now start the Cloud C2 server
- c2-3.5.2_amd64_windows.exe -hostname <ip_addr_of_VM>
       
7. Setup the Network to run the server over
- First take the Netgear GS308 Switch and a Mini Target PC out and plug them into power
- Use the Ethernet port on your laptop or use an USB to Ethernet adapter to connect to the Switch over Ethernet(wired)

8. Next Setup the Wireless access point
- First take out Asus RT-N66U Dark Knight and plug it into power(NOT THE SWITCH YET)
- Power on the router
- Hold RESET button (back) for 10 seconds, the wait for reboot
- Plug your latop into one of the yellow lan port on the back of the device
- Open a browser and go to http://192.168.1.1
- Log in to the software and go to Adminisration>Operation Mode
- Select: Access Point Mode -> Save / Apply(Router will reboot)
- Connect to the Router by the browser
- Go to Wireless Settings
- Set SSID: <any_valid_network_name>
           
8.Configure Virtual Machine Network Adapter
- Set Adapter 1: Intel PRO/1000 MT Desktop (Bridged Adapter, Intel(R) Wi-Fi 6E AX211 160(MHz)
- Set Adapter 2: Intel PRO/1000 MT Desktop (Bridged Adapter, Realtek USB GbE Family Controller)






