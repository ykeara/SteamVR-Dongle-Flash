# SteamVR-Dongle-Flash
A simple Guide and batch script to flash steam controller dongles to watchman dongles for SteamVR/OpenVR

## Tested and Working
 - As Of 4/26/19
 
## Requirements

- A steamVR controller Dongle purchasable on ~~[Steam](https://store.steampowered.com/app/530260/Steam_Controller_Wireless_Receiver/)~~
  - [alternative dongle](https://www.virtualbuilds.com/product-page/usb-wireless-receiver-dongle) I haven't tried but should work, since dongle no longer purchaseable from steam.
  - [alternative dongle 2](https://tundra-labs.com/shop/vive-dongle) Just Vive Dongles sold by 3rd party.
- SteamVR installed on your computer

## WARNING

- Please Assume this change is permanent
- This will flash ALL CONNECTED dongles, remove any before hand that you don't want flashed.

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
- **This should be considered permanent** In theory its not but I can't seem to find anyone who has successfully flashed firmware back, and my own attempts are unsuccssful.
- There is a firmware that will Permanatly change the dongle, but you must be signed up for the SteamVR HDK Directions on how to do so can be found [here](https://partner.steamgames.com/vrlicensing)

## Batch File
- The Batch File is designed as a one click solution to do it for you.
  - **NOTE** the batch file only works if Steam and SteamVR are installed to default directories in the C: drive.

## What should I see

- If the command is run you should see something similiar to this image:

![Dongle Firmware](/res/donglefirmware.png)

## Issues

This program changes the runtime firmware but not the bootloader

If you re-ender the bootloader (by doing a firmware update) it will boot up as a steam controller dongle waiting for firmware, Steam sees that and "recovers" it to be a steam controller dongle.

Which would require you to run this program again.

`tools\lighthouse\firmware\vr_controller\archive\htc_vrc_dongle_1461100729_2016_04_19.bin` only contains the runtime firmware

a bin file containing both the runtime and the bootloader firmware can be acquired by becoming following the steps at [https://partner.steamgames.com/vrlicensing]
- [Sign up as a Steam partner](https://partner.steamgames.com/)
- [Sign up as a SteamVR Tracking licensee](https://partner.steamgames.com/pub/vrtrackingonboarding)
- Install the SteamVR Tracking HDK steam://install/507090/

the file is now available at `Steam\steamapps\common\SteamVR Tracking HDK\firmware\dongle\watchman_dongle_combined.bin`

you can now follow the steps described in the [ReadMe](https://github.com/ykeara/SteamVR-Dongle-Flash/blob/master/README.md)
but instead flashing the new file:

- open a Command Prompt (cmd or power shell)
- Navigate to where SteamVR app is installed on your computer (default is: C:\Program Files (x86)\Steam\steamapps\common\SteamVR)
  - Powershell CMD - `cd 'C:\Program Files (x86)\Steam\steamapps\common'`
- Run the Command `SteamVR\tools\lighthouse\bin\win32\lighthouse_watchman_update.exe -D SteamVR Tracking HDK\firmware\dongle\watchman_dongle_combined.bin`
- Restart Steam, plug your dongles in, close the command prompt/powershell and you should be good to go!
