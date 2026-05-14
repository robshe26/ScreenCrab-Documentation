# Screen Crab Deployment and Detection

Objective:
To understand the physical deployment of a hardware-based man-in-the-middle HDMI interception device and apply defensive strategies to detect its presence. 

## Step 1: Physical Deployment & Local Capture

Establish the physical MITM connection and verify local interception

1. Inline Placement: Disconnect the monitor from the target computer. Connect an HDMI cable from the target computer to the HDMI in port on the Screen Crab

3. Moniotr Connection: Connect a seconf HDMI cable from the HDMI out port on the Screen Crab to the external monitor.

5. Power Up: Insert the MicroSD card and provide power to the Screen Crab. Ensure the video singal successfully passes through to the monitor, appearing normal to the end-user.

7. Verify Interception: Allow the target computer to run for a few minutes. Safely power down the Screen Crab, remove the MicroSD card, and review the captured screenshots or video files to confirm successful local data collection. 

## Step 2: Remote Configureation and C2

Establish a covert wireless connection for remote management. 

1. Wi-Fi Configuration: Configure the device's network settings to connect to the designated testing Wi-Fi network.

2. Cloud C2: Link the Screen Crab to your Hak5 Clpid C2 instance.

3. Remote Operations: Log into the Cloud C2 dashboard. Verify that you can view the live HDMI stream and remotely adjust the screenshot capture intervals without physically interacting with the device.

## Step 3: Detection

Identify Indicators of Compormise 

1. Display Signature Analysis: Open the display settings on the target computer. Check the connected monitor's harware profile. Not any discrepancies, such as a generic display interface name replacing the actial monitor brand, or an unexplained restriction in the available screen refresh rates.

2. Network Monitoring: Analyze the local wireless network traffic. Identify outbound connectins originating from the device communicating with the external Cloud C2

## Lab Deliverables:

Draft a incident report detailing;

1. The type of data successfully intercepted during Step 1.

2. The specific display signature anomalies discovered on the target machine during Step 2.

3. Recommendations for mitigating physical hardware attacks in a standard office envrionemnt. 
