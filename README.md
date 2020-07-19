# Lenovo Thinkpad T470s 
## Opencore Hackintosh

***It should go without saying but I will say it anyway. Hackintoshing is dangerous and could ruin your hardware permanently and I take no responsibility for your stuff. These materials are only provided as an academic curiosity, please Hackintosh at your own risk. No guarantees are implied and no relationship is established between the users of this repo and myself. I own nothing, everything belongs to Apple/Lenovo/OpenCore Team. Thanks.***

I'm creating this repository for those who might be trying to Hackintosh a computer that is similar to mine. I have reached what I beleive to a moderate level of stability with this EFI, and I am unlikely to update this repo until after the puclic release of MacOS 11 Big Sur. Happy Hacking! 

Currently running Mac OS 10.15.6 Catalina on OC 0.5.9

### Hardware Config: 

1. Make and Model: Lenovo Thinkpad T470s
2. Processor and Chipset: Intel Core i5 6300u / Intel Skylake 100 series chipset
3. Graphics: Intel HD 520
4. Monitor: 1080p with Multi-touch 
5. Storage: HP ex920 NVMe 1 TB SSD
6. RAM: 12 GB DDR4
7. 1 x PS/2 Trackpad + Trackpoint 
8. 1 x PS/2 Keyboard
9. 1 x USB 3.0 card reader
10. 3 x USB 3.0 type a ports
11. 1 x TB3/USB C port
12. 1 x HDMI port
13. 1 x 3.5mm mic/headphone jack
14. 1 x smart card reader
15. 1 x WWAN network sim


### Currently functioning:

1. All basic functions including sleep/wake and boot without error including iCloud Services and Wired Ipad Sidecar
2. Trackpoint and Trackpad with gesture support and Keypad buttons function as well
3. Touchscreen
4. Cardreader @ usb 3.0 speeds
5. USB type A ports with USB 3.0 and USB 2.0 support
6. TB3 (Alpine Ridge)/USB type C works. However the ports have only been tested with standard USB 3.0 devices, since I do not posess any working TB3/USB3.1 devices and therefore cannot test. 
7. HDMI output is quirky, it works but settings have to be tuned. 

### Untested

1. BT/Wifi - My card is on order and I will update the system with appropriate Kexts once it is delivered. 
2. WWAN
3. Smart Card Reader
4. Audio over HDMI

**Note on Keyboard Shortcuts**

Due to system instability being caused by SSDT-KBD.aml, I have removed the ssdt and replaced it with a couple of smaller SSDTS with more circumscribed functionality. Currently on Volume Controls and Brightness Controls are working as intended on the Laptop Keyboard. I am unlikely to bother further improving this. 


## Installation Instructions:

1. Please follow Dortania OpenCore Vanilla guide to create ACPI, gather Kexts, and create installer. I would recommend reading through the entire process even if you are going to just copy paste this repo into your EFI folder; it will give you the ability to debug and upgrade your OC install in the future. 
2. For those of you with a different CPU please use the post-install guide on Power Management how to generate new CPUFriendFreind.kext. 
3. To enable Apple services for you computer, you must fill in the
   - Serial Number/ MLB/ SmUUID which are currently blank on the EFI 
   - Please refer to config.plist guide on OC configuration on how to properly generate this information for your hackintosh. 
4. The EFI uses the debug version of OC 0.5.9, however the debug options have been turned off. Please refer to OC Debugging page on instruction about turning this back on. 

**BIOS Settings**

1. Config 
   - USB UEFI Bios Support -> Enabled
   - Keyboard Mouse
     - Trackpoint -> Enabled
     - Trackpad -> Enabled
   - Display
     - Total Graphics Memory -> 512 MB
     - Boot Time Extension -> Disabled
   - Thunderbolt 2
     - Wake by TB3 -> Disabled
     - Support in Preboot Env -> Enabled
2. Security
   - Fingerprint 
     - Predesktop Auth -> Disabled
     - Security Mode -> Normal
   - Security Chip
     - TPM 2.0
     - Security Chip -> Disabled/All
   - Memory Protection -> Enabled
   - Virtualization
     - Intel Virtualization -> Enabled
     - Intel VT -d -> Disabled
   - I/O port access -> Enable All
   - Secure Boot -> Disabled
   - Intel SGX -> Disabled
   - Device Guard -> Disabled   
3. Startup
   - UEFI/Legacy -> Legacy only
   - CSM Support -> No
   
   
### Credits

1. [Opencore Dortania Install Guide](https://dortania.github.io/OpenCore-Install-Guide/)
2. [Opencore Hotpatching Guide](https://github.com/jsassu20/OpenCore-HotPatching-Guide)
3. [Altairko Clover T470s Repo](https://github.com/Altairko/Lenovo-T470s-Clover)
4. [YBS-Juan OC T470s Repo](https://github.com/YBN-JUAN/T470s-OpenCore-EFI)
5. [Digitalec Clover T470 Repo](https://github.com/digitalec/thinkmac-t470)
