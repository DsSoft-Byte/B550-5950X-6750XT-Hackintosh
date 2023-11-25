# Hackintoshing my daily driver desktop

Components
1. Gigabyte/Aorus B550 Elite V2
2. AMD Ryzen 5950X
3. AMD Radeon RX 6750XT (Fully working thanks too NootRX)
4. 64GB Corsair LPX RAM
5. Gigabyte GC-WB1733D-I WiFi Card. (Fully working at full speed with bluetooth thanks to AirportITWLM)

# Differences

Preinstall EFI For Install and Setup

PostInstall EFI For USB Booting with GPU Acceleration

PostInstall 100% Has fixed blackscreen issues and NO Verbose boot, no keepsysm and debug=0x100 boot flag. Also no Mismatched RAM Eror and CPU shows up as geniuine Ryzen

PostInstall 110% is the same like 100% but with fixed power management.

Fully Working with sleep, iMessage and Apple ID sign-in.
My "Line Out" Audio is mapped as "Internal Speakers", it works however.
Sonoma installation not possible because normal itwlm does not init and AirportItwlm panics the boot.
Fully working on Latest Ventura 13.6.1.

# Use The Preinstall EFI when installing and on the setup too!
There is a issue with Lilu and NootRX on the last setup stage, the only option is to use WhateverGreen (VESA mode) during the installation and setup stages and then booting the 100% ready system with NootRX later.

1. Preinstall Has Lilu+WhateverGreen with required boot-args
2. PostInstall Has Lilu+NootRX with required boot-args

One could also add the RestrictEvents kext to stop the mismatched RAM notification on MacPro7,1 SMBIOS (It will get confused because 7,1 only has 3 RAM slots and many desktops including mine use 4 DIMMS), i however like it this way.

# Half the GPU-Related boot-args are useless (probably) but im too scared to delete them
Thats for you to find out if you have time.
