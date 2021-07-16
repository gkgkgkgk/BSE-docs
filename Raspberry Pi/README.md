# Raspberry Pi

## SSH/Headless setup for Raspberry Pi

### Prerequisite - Installing the OS
- [Download Raspberry Pi Imager](https://www.raspberrypi.org/software/)
- make sure microSD is inserted to your computer with the microSD Reader or in the UGREEN SD/microSD Reader
- Select OS: Raspberry Pi OS (32-bit)
- Select Storage: microSD (E:\ or D:\ for Windows)
- Click Write and Wait!
- Eject microSD after Write is completed and plug back into the computer!

### Installation
#### Step 1 - Setting Up the Pi
Navigate to the microSD folder (could be called **boot**)  
add a file called **ssh** and **wpa_supplicant.conf**  
edit **wpa_supplicant.conf** and add:
```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
country=<Insert 2 letter ISO 3166-1 country code here>
update_config=1

network={
 ssid="<Name of your wireless LAN>"
 psk="<Password for your wireless LAN>"
}
```
on MacOS/Linux Terminal:  
`touch ssh`  
`touch wpa_supplicant.conf`  
`nano wpa_supplicant.conf`  

on Microsoft Command Prompt:  
`echo > ssh`  
`echo > wpa_supplicant.conf`  

```
SOME IMPORTANT NOTES:
---------------------
- make sure you do not leave a file extension
    i.e.
        ssh.txt or ssh.docx

- the ISO 3166-1 Country Code for the US is "USA" not "US"
```

#### Step 2 - Turning on the Pi
After loading up the two files from step 1, eject the microSD and plug it into the Raspberry Pi.  
Turn on the Raspberry Pi, and you should see a static red light and a static-to-flickering green light.  

```
SOME IMPORTANT NOTES:
---------------------
- do NOT have the raspberry pi on when inserting any new peripherals (this also includes inserting microSDs)
this could lead to corruption / hardware damages!
```

#### Step 3 - Connecting with SSH
Default Username: `pi`  
Default Password: `raspberry`  

##### For Windows
Install [PuTTY](https://www.putty.org/) for SSH  
Host Name: `raspberrypi.local`  
Port: `22`  

#### For MacOS / Linux
`ssh pi@raspberrypi.local`  

#### Step 4 - Enabling VNC (Optional)
This enables [VNC](https://www.realvnc.com/en/connect/download/viewer/)  
In the Raspberry Pi Terminal:  
```sudo raspi-config```  
Go to **Interface Options** -> **VNC** -> **Enable**  
Then reboot with ```sudo reboot```