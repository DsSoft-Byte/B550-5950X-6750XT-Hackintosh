# B550 Hackintosh

Components
1. Gigabyte/Aorus B550 Elite V2 (rev 1.2)
2. AMD Ryzen 5950X (Any 16 Core AMD CPU should work on B550 with this patching tho)
3. AMD Radeon RX 6750XT (Fully working thanks to NootRX)
4. 64GB Corsair LPX RAM
5. Gigabyte GC-WB1733D-I WiFi Card (Sonoma only)
6. Realtek RTL8125 Ethernet Card (Tahoe only)

My "Line Out" Audio is mapped as "Internal Speakers", it works however.

alcid=3 for this board

# What does NOT work
1. Sleep, Edge case scenario for me as my GPU has a very weird RGB controller that is NOT i2c but rather behaves like USB, is impossible to Map. This will probably apply only to MSI Radeon 6XXX Series with RGB. I have the 6750XT Gaming Trio X, it also doesnt work on Linux tho.

2. Apple Music FairPlay Audio. AppleTV, Netflix, Amazon Prime, Spotify all work, apple music pretends to play but doesnt.


# Differences
For Sonoma and Lower use the "EFI Sonoma AIO V2" in Sonoma Directory. for Higher version use the Tahoe EFIs. Tahoe EFIs were updated to a newer OpenCore version, changed bootargs a bit for audio to work and updated kexts. the EFI_Performance has Shanee's mttr patches enabled and Algrey's disabled. Essentially quadrupling the GPU Performance. Not recommended when using HDMI or DisplayPort audio. The recommended EFI as of now is the Tahoe EFI_Performance.


# Tahoe+ Audio Patching
For a native like experience i use AppleALC with the AppleHDA backport (Removed in Tahoe). Use MyKextInstaller to install it. The Tahoe EFI has SIP set to disabled, even after resetting nvram 5 times that didnt work for me so boot into MacOS Recovery from OpenCore and set csrutil disable if needed. Reboot and profit from crisp and crystal clear audio.

# Half the GPU-Related boot-args are useless (probably) but im too scared to delete them
Thats for you to find out if you have time.

# Resizable Bar support
It works, to even boot Sonoma AIO V2 EFI and Tahoe EFI you need Above 4G decode enabled and Re-Bar Auto/On
