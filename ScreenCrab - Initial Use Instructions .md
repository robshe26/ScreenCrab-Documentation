# ScreenCrab - Initial Use Instructions



## Use without Cloud C2 software 

- This is documentation for the use of the `Screen Crab` device without the use of Hak5's `Cloud C2` 

## Initial Setup

1. Format a MicroSD card in the file system **exFAT**, for cards larger than 64Gbs or **FAT32** for cards up to 32Gbs 

2.  Insert the SD card into the Screen Crab so it can write a config.txt file to the root of the card

3. Then insert the MicroSD back into a MicroSD reader on your personal computer 

___The files that you see should resemble the picture below___
<img width="1510" height="537" alt="Screenshot 2026-02-24 190657" src="https://github.com/user-attachments/assets/f1f5491e-9d16-41e9-a9e3-982a8b4fee06" />


4.  In the config.txt file the default configuration should appear like this: 

        LED ON
        CAPTURE_MODE IMAGE
        CAPTURE_INTERVAL 5
        STORAGE FILL
        BUTTON EJECT

5. These configurations can be changed for different goals/outcomes: 

        LED [ON, OFF]

        CAPTURE_MODE [IMAGE, VIDEO, OFF]         (LED indication: Image=Blue, Video=Yellow, Off=Off)

        DEDUPLICATE [ON, OFF]  (Only for IMAGE CAPTURE_MODE)

        CAPTURE_INTERVAL [N] (in N seconds)
  
        STORAGE [ROTATE or FILL]
  
        BUTTON [EJECT, OFF]

        VIDEO_BITRATE [LOW, MEDIUM, HIGH]
        (low 2Mbps, medium 4Mbps, high 16Mbps)

___ 
### Changing the Configuration


-  Changing the config.txt file is relatively simple:
	- Open the config file in an application such as notepad 
	- Make changes to default configuration
 

*An example of this .txt file changed into video mode is as follows:*

        LED OFF

        CAPTURE_MODE VIDEO

        CAPTURE_INTERVAL 30
  
        STORAGE_FILL

        BUTTON EJECT

        VIDEO_BITRATE MEDIUM

___Example of the config.txt file:___
<img width="2875" height="1696" alt="Screenshot 2026-02-24 190748" src="https://github.com/user-attachments/assets/e26f335f-1fc1-4d0e-ab6c-5dfed0128c6f" />

___

## [LED Status Indications] (https://docs.hak5.org/screen-crab/getting-started/led-status-indications/#configuration-status)

##### STARTUP STATUS 
- LIGHT CYAN (SHORT)
    - Device received power, starting boot
- BLINKING GREEN
    - Waiting for capture to complete, ejecting SD card
Removing the MicroSD card before the LED lights solid green may damage the card’s format.
- SOLID GREEN
    - (After light cyan) Booting
    - (After button push) SD is safe to eject
- SOLID RED
    - SD card full or not detected
##### CONFIGURATION STATUS 
- BLINKING CYAN
    - Updating device wireless to match MicroSD `config.txt`
    - Updating device wireless state to match MicroSD config.txt
        - Changing from wireless disabled -> wireless enabled
        - Changing from wireless enabled -> wireless disabled
- SOLID MAGENTA
    - Device button listening for capture override
- INVERSE BLINK MAGENTA
    - Button pushed once during capture override mode at startup - config set to default image capture
    - Button pushed twice during capture override mode at startup - config set to default video capture
##### CAPTURE STATUS: 
- SOLID BLUE
    - Has video signal and capturing images to SD card
- SOLID YELLOW
    - Has video signal and capturing video to SD card
- SOLID WHITE
    - Has no video signal
##### UPGRADE STATUS:
- BLUE/RED POLICE PATTERN
    - Screen Crab detected _`upgrade.bin`_ on MicroSD card at boot - starting device upgrade
- BLUE/MAGENTA POLICE PATTERN
    - Screen Crab starting framework upgrade
- FOREVER BLINKING RED - only during device upgrade (following police pattern)
    - Software Upgrade Failed
___

## Basic Capturing 

1. Once the MicroSD card is properly formatted with both by the user and the Screen Crab, insert the MicroSD back into the screen crab 

2. Then connect the Screen Crab to the intended target using two HDMI cables and a USB-C for power 
	   - After a brief 30-second boot time, the Screen Crab LED with light blue to indicate that the MicroSD card is being written to with screenshots. To stop recording and eject the MicroSD card - press the button, with for the LED to light solid Green, then eject the card. 

3.  Make note of the LED Status Indications indicated above, and wait for the desired screen captures 

___

## Loot/Captures Investigation 

1. Once the desired captures are obtained, remove the MicroSD from the Screen Crab and insert it to a MicroSD reader on a different machine. 
2. There should be a folder named Loot as shown in the screenshot found above.
3. Upon opening the folder you should see a list of .jpg images or .mp4 files based on the initial configuration

___The Loot folder should appear similar to this:___
<img width="2855" height="1762" alt="Screenshot 2026-02-24 183103" src="https://github.com/user-attachments/assets/1a1ab506-8701-478d-b1c0-a9bac289919a" />



