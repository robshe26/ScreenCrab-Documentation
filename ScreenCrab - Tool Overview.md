# Screen Crab - Tool Overview

- This document holds a description of the tool `Screen Crab`, and its uses.

## Overview 

The Screen Crab is a stealthy video man-in-the-middle implant. It sits between HDMI devices such as a computer or monitor to quietly capture screenshots. This is a hardware based tool, meaning unlike software-based screen recorders it cannot be detected by task manager or antivirus. 

## How it Works: The Hardware

The Screen Crab sits physically between a source device and a monitor 
- Physical Setup: You plug the HDMI cable from the computer into the "Input" port of the Screen Crab, and then run another HDMI cable from the "Output" port to the monitor.
- Passthrough: It provides a lag-free, 1080p video signal to the monitor, so the user has no idea thier feed is being viewed.
- The Data Collection: While passing the signal through, it silently captures screenshots or video and saves them to an onboard microSD card or streams them over Wi-Fi. 

## Capabilities

The Screen Crab is designed for persistence and remote operations in many scenarios 

A. Screenshot and Video Mode
  - You can configure the device to take a screenshot every few seconds, or record full-motion video

B. Remote Streaming and Cloud C2
  - Due to the tool's ability to connect to Wi-Fi you can connect it to Hak5's Cloud C2 platform. This then allows you to
      - View a live stream of the screen from anywhere in the world
      - Change capture setting remotely
      - Exfiltrate the loot without needing to physically retrieve the SD card.
   
## Primary Use Cases

- Penetration Testing:
    - Physical red-teaming where an agent gains brief access to a room and can then monitor a workstation
- System Administration:
    - monitoring systems of kiosks where software installation is prohibited
- Evidence Collection
    - Capturing visual proof of unauthorized activity on a specific terminal 
