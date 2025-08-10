# USB Solutions

Fixing a corrupted or malfunctioning USB flash drive is easier than ever. This repository provides a step-by-step tutorial to help you: Whether you're dealing with a stubborn flash drive or just want to learn the recovery process, this guide walks you through everything you need to know.

## [ 1 ] Method - Check by Utility Feature (If your USB Device Shows in This PC)
  1. Plug in Your USB Drive.
  2. Open This PC (File Explorer).
  3. Right-click on Drive and Select Properties.
  4. Go to "Tools" Tab > Click 'Check' Button.
  5. Click "Scan and repair drive" Option.

## [ 2 ] Method - If the USB Drive is not showing in This PC
  1. Start > Open (Device Manager).
  2. Under 'Disk Drive' Dropdown > Right-click on your specific USB Device.
  3. Select 'Enable Device'

  ### OR ( If your Device is Already Enabled ) then

  3. Select 'Update Driver'
  4. Select 'Search Automatically for Drivers' Option >
  5. Select 'Search for updated drivers on Windows Update' (If 4 Step: "The best driver for your device are already installed" Show!)

  ### OR you can try to Reinstall USB Driver
  
  3. Select 'Unstall Device'
  4. Restart your PC.
  5. Your computer will automatically reinstall the flash drives.

  
  

## How to Open Command Prompt as Administrator. 

```bash
Right-click on "Command Prompt" > Left-click on "Run as administrator." 
```

## [ 1 ]  Using ChkDsk

```bash
chkdsk /X /f G:
```
(Replace G: with your pen drive's letter) and press Enter.

You can also try

```bash
chkdsk G: /f /r /x
```
(adds /r to recover data from bad sectors).








