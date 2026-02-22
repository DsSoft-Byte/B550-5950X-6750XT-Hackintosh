# B550 Hackintosh

Components
1. Gigabyte/Aorus B550 Elite V2 (rev 1.2)
2. AMD Ryzen 5950X (Any 16 Core AMD CPU should work on B550 with this patching tho)
3. AMD Radeon RX 6750XT (Fully working thanks to NootRX)
4. 64GB Corsair LPX RAM
5. Gigabyte GC-WB1733D-I WiFi Card (Sonoma only)
6. Realtek RTL8125 Ethernet Card (Tahoe only)

My "Line Out" Audio is mapped as "Internal Speakers", it works however.

# What does NOT work
Sleep, Edge case scenario for me as my GPU has a very weird RGB controller that is NOT i2c but rather behaves like USB, is impossible to Map. This will probably apply only to MSI Radeon 6XXX Series with RGB. I have the 6750XT Gaming Trio X, it also doesnt work on Linux tho.


# Differences

Disregard the Irrelevant testing EFIs, they shouldnt be needed, if something doesent work on during install on Pre Sonoma MacOS use the EFI PreInstall, for Sequoia and up just use the Tahoe EFI as is, its good enough.

1. Preinstall Has Lilu+WhateverGreen with required boot-args
2. PostInstall and Tahoe EFIs have Lilu+NootRX with required boot-args

One could also add the RestrictEvents kext to stop the mismatched RAM notification on MacPro7,1 SMBIOS (It will get confused because 7,1 only has 3 RAM slots and many desktops including mine use 4 DIMMS), i however like it this way.

# Half the GPU-Related boot-args are useless (probably) but im too scared to delete them
Thats for you to find out if you have time.

# Resizable Bar support
It works, to even boot Sonoma AIO V2 EFI and Tahoe EFI you need Above 4G decode enabled and Re-Bar Auto/On
