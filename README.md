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
