# Hackintoshing my daily driver desktop

Components
1. Gigabyte/Aorus B550 Elite V2 (rev 1.2)
2. AMD Ryzen 5950X
3. AMD Radeon RX 6750XT (Fully working thanks too NootRX)
4. 64GB Corsair LPX RAM
5. Gigabyte GC-WB1733D-I WiFi Card. (Fully working at full speed with bluetooth thanks to AirportITWLM)

My "Line Out" Audio is mapped as "Internal Speakers", it works however.
Sonoma installation not possible because normal itwlm does not init and AirportItwlm panics the boot.
Fully working on Latest Ventura 13.6.1.

# What does NOT work
Sleep, Edge case scenario for me as my GPU has a very weird RGB controller that is NOT i2c but rather behaves like USB, is impossible to Map. This will probably apply only to MSI Radeon 6XXX Series with RGB. I have the 6750XT Gaming Trio X.

Sleep will work for you on the 120% EFI if you have the Aorus B550 Elite V2 (rev 1.2) Motherboard. Its just a MSI Skill issue. If you have a B550 Board that is NOT my exact model, hell even a different revision like rev 1.3 you might run into issues as the PCB was redesigned. All other B550 motherboards should use the 110% EFI and map their ports themselves. (Hackintool Kext method)


# Differences

Preinstall EFI For Install and Setup

PostInstall EFI For USB Booting with GPU Acceleration

PostInstall 100% Has fixed blackscreen issues and NO Verbose boot, no keepsysm and debug=0x100 boot flag. Also no Mismatched RAM Eror and CPU shows up as geniuine Ryzen

PostInstall 110% is the same like 100% but with fixed power management.


# Use The Preinstall EFI when installing and on the setup too!
There is a issue with Lilu and NootRX on the last setup stage, the only option is to use WhateverGreen (VESA mode) during the installation and setup stages and then booting the 100% ready system with NootRX later.

1. Preinstall Has Lilu+WhateverGreen with required boot-args
2. PostInstall Has Lilu+NootRX with required boot-args

One could also add the RestrictEvents kext to stop the mismatched RAM notification on MacPro7,1 SMBIOS (It will get confused because 7,1 only has 3 RAM slots and many desktops including mine use 4 DIMMS), i however like it this way.

# Half the GPU-Related boot-args are useless (probably) but im too scared to delete them
Thats for you to find out if you have time.

# Resizable Bar support
It works, the EFIs are made with it disabled though, you will need to set ResizeAppleGPUBars to 0 and then it will work.
