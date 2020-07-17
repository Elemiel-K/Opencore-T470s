# Opencore-T470s

I'm creating this repository for those who might be trying to Hackintosh a computer that is similar to mine. I will continue to update the repository every few weeks/months as I improve my ACPI and Kext loadout. 

Currently running 10.5.6 Catalina on OC 0.5.9

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

1. All basic functions including sleep/wake and boot without error 
2. Trackpoint and Trackpad with gesture support and Keypad buttons function as well
3. Touchscreen
4. Cardreader
5. USB type A ports
6. USB type C works if you boot with device inserted

### Non functional:

1. TB3 bus
2. WWAN card
3. Smart Card

### Untested

1. BT/Wifi - My card is on order and I will update the system with appropriate Kexts once it is delivered. 


**Note on Keyboard Shortcuts **

With the use of software called Thinkpad Assistant along with associated ACPI files I've been able to get much functionality out of shortcut keys such as volume control and brightness control. This is still a work in progress and will not be updated along with the repo, please google the software if you are interested. 


## Installation Instructions:

Please follow OC Vanilla guide to create ACPI, gather Kexts, and create installer. I would recommend reading through the entire process even if you are going to just copy paste this repo into your EFI folder; it will give you the ability to debug and upgrade your OC install in the future. 


**BIOS Settings **

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
   - CSM Support -> Yes
