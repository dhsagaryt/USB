# USB Solutions

Fixing a corrupted or malfunctioning USB flash drive is easier than ever. This repository provides a step-by-step tutorial to help you: Whether you're dealing with a stubborn flash drive or just want to learn the recovery process, this guide walks you through everything you need to know.

## [ 1 ] Method - Check by Utility Feature (If your USB Device Shows in This PC)
  1. Plug in Your USB Drive.
  2. Open `This PC` (File Explorer).
  3. Right-click on your specific Drive and Select `Properties`.
  4. Go to "`Tools`" Tab > Click '`Check`' Button.
  5. Click "Scan and repair drive" Option.

## [ 2 ] Method - If the USB Drive is not showing in This PC
  1. `Start` > Open (`Device Manager`).
  2. Under '`Disk Drive`' Dropdown > Right-click on your specific USB Device.
  3. Select '`Enable Device`'

  ### OR ( If your Device is Already Enabled ) then

  3. Select '`Update Driver`'
  4. Select '`Search Automatically for Drivers`' Option >
  5. Select '`Search for updated drivers on Windows Update`' (If 4 Step: "The best driver for your device are already installed" Show!)

  ### OR ( Try to Reinstall USB Driver )
  
  3. Select '`Unstall Device`'
  4. Restart your PC.
  5. Your computer will automatically reinstall the flash drives.

## [ 3 ] Method - Using CMD by CHKDSK Command

The CHKDSK command (short for "check disk") is a built-in Windows utility used to scan a hard drive for file system errors and bad sectors.

### Open Command Prompt as Administrator

> Start > Right-click on "`Command Prompt`" > Left-click on "`Run as administrator`" 

### Simple CHKDSK Command (Basic)

```bash
chkdsk G: /f /r
```
(Replace G: with your pen drive's letter) and press Enter.

Note: If CHKDSK cannot lock the volume, you may be prompted to dismount it. Type "`Y`" and press Enter to allow it.

- `/f:` Fixes errors on the disk. This is often used in conjunction with `/r.`
- `/r:` Locates bad sectors and recovers readable information. It also implies `/f.`
- `/x:` Forces the volume to dismount first, if necessary, to perform the check. This also implies `/f.`
- `/v:` Displays the name of each file in every directory as the disk is checked.
- `/scan:` Runs a real-time scan for file system errors without requiring a restart.

You can also try

```bash
chkdsk G: /f /r /x
```

(Replace G: with your pen drive's letter) and press Enter.

Note: If CHKDSK cannot lock the volume, you may be prompted to dismount it. Type "`Y`" and press Enter to allow it.

## [ 4 ] Method - Using CMD by DISKPART Command (Advanced)

Diskpart is a command-line disk partitioning utility in Windows. It allows users to manage disks, partitions, and volumes through commands typed in the command prompt. It can be used to create, delete, format, and manage partitions, as well as assign drive letters and mount points.

### Open Command Prompt as Administrator

> Start > Right-click on "`Command Prompt`" > Left-click on "`Run as administrator`" 


Type
```bash
diskpart
```
AND PRESS `Enter`.


```bash
list disk
```
to identify your pen drive's disk number.


```bash
select disk X 
```
(replace X with the disk numerical number). and press `Enter`.


```bash
clean
```
and press `Enter`. to remove all partitions and data.


```bash
create partition primary
```
and press `Enter`. to create a new partition.

### Activate Partition (For Bootable Drive)

```bash
active
```
and press `Enter`. to designate a specific partition on a disk as the "active" partition.

- How to Mark Partition as Active with Easy Steps🔥The active command in Diskpart is used to mark a primary partition as active, which is crucial for booting the operating system on a BIOS-based system. When a computer starts, the BIOS looks for an active partition to load the operating system from. Marking a partition as active tells the BIOS which partition contains the necessary boot files. On UEFI systems, the EFI System Partition is used for booting, and the active command is generally not used.

### Format Drive (Choose Any One of Them)

```bash
format fs=fat32 quick
```
```bash
format fs=exfat quick
```
```bash
format fs=ntfs quick
```
and press `Enter`. 

(Choice One Option depending on your needs) to format the drive.

- NTFS is the superior choice due to its features and performance. FAT32 is best suited for removable storage devices where maximum compatibility is needed. ExFAT is a good middle ground for large files and cross-platform compatibility, but it may be less reliable than NTFS. [read more](https://github.com/dhsagaryt/USB/blob/main/Different%20File%20Systems%20(NTFS%2C%20FAT32%2C%20ExFAT).md).

### Assign a Drive Letter for (File Explorer). 

```bash
assign
```
and press `Enter`. to assign a drive letter.

```bash
exit
```
and press `Enter`. to exit DISKPART. 
















