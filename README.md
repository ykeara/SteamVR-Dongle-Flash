# SteamVR-Dongle-Flash
A simple Guide and batch script to flash steam controller dongles to watchman dongles for SteamVR/OpenVR

## Tested and Working
 - As Of 4/26/19
 
## Requirements

- A steamVR controller Dongle purchasable on [Steam](https://store.steampowered.com/app/530260/Steam_Controller_Wireless_Receiver/)
- SteamVR installed on your computer

## Guide

- Remove ALL SteamVR dongles, including the HMD.
- Exit Steam
- Plug in your Steam Controller Dongle to a USB.
- open a Command Prompt (cmd or power shell)
- Navigate to where SteamVR app is installed on your computer (default is: C:\Program Files (x86)\Steam\steamapps\common\SteamVR)
  - Powershell CMD - `cd 'C:\Program Files (x86)\Steam\steamapps\common\SteamVR'`
- Run the Command `tools\lighthouse\bin\win32\lighthouse_watchman_update.exe -D tools\lighthouse\firmware\vr_controller\archive\htc_vrc_dongle_1461100729_2016_04_19.bin`
- Restart Steam, plug your dongles in, close the command prompt/powershell and you should be good to go!

## Notes

- You should be able to flash multiple dongles at once, and not need to remove old ones, but as general precaution I advise against it.
- This does not replace the bootloader so in theory you can convert your watchman Dongle back into a controller Dongle, But I have not tested.
- There is a firmware that will Permanatly change the dongle, but you must be signed up for the SteamVR HDK Directions on how to do so can be found [here](https://partner.steamgames.com/vrlicensing)

## Batch File
- The included Batch File should work as a 1-click solution Assuming the **Default** install locations (Steam installed on C: drive, and SteamVR installed there as well.

## What should I see

- If the command is run you should see something similiar to this image:

![Dongle Firmware](/res/donglefirmware.png)
