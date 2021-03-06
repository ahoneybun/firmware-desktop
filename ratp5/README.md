# To update your firmware:

1. Backup all data. There is a small possibility that updating firmware can cause data loss.

### Downloading and preparing new firmware
1. Updating firmware requires a flash drive at least 2 GB in size.
2. The firmware.rom file needs to be placed on a thumbdrive with MBR FAT32 formatting.
3. Feel free to skip ahead to the later sections if this is familiar ground.
4. To properly format a flash drive, follow the next instructions:

### Preparing Flash Drive
1. Plug in the flash drive.
2. Open the "Disks" program.
3. The left panel of the "Disks" application shows all of the drives connected to your machine. Select the flash drive.
4. Select the menu button in the top right corner. Select "Format Disk".
5. A pop-up will appear asking how the drive should be formatted. The defaults are desired so select "Format...".
6. Confirm the execution by selecting "Format".
7. Once this process is complete, the volume should be listed as "Free Space".
8. Select the "+" button to create a partition for this drive.
9. The default settings should be sufficient. A name for the partition can be added to help identify the use of the drive.
10. Select "Create". The drive should be labeled with the name(if any) as well as the size and the parition type, FAT.
11. Mount the drive by selecting the "Play" button.
12. When the drive is ready, download the `firmware.rom` file from here: [ratp5 firmware](https://github.com/system76/firmware-desktop/blob/master/ratp5/firmware.rom). Click `Download` to begin the download.

13. The sha512sum checksum for this download is:
```0f293a353725ba1578a6d989289d8a6cf10cfc605822c9559cc889013641e5bd3082b5ce99166396cb98eb5debe0cc0605cec63ff41ad651aa00d4fca04ca8a8```.

    Confirm that the download has the same checksum by executing the following command in the firmware.rom directory:

    `sha512sum -b firmware.rom`

14. Copy over the firmware file to the flash drive.

### Writing new firmware
1. After saving and backing up the machine, make sure the flash drive with the updated firmware is plugged into the computer.
2. Power off the machine.
3. Power back on the machine. As the machine is powering back up, hold down the 'Del' key.
4. After the System76 logo is shown, the Gigabyte BIOS will appear. 
5. Press `F8` to start the QFlash utility.
6. Select `Update BIOS from Drive`.
7. Select the flash drive with the firmware on it.
8. Select the `firmware.rom` file.
9. The QFlash will take a few seconds to verify the file. 
10. The BIOS version, BIOS date, as well as checksum for the new firmware will then be displayed. The option between `Normal Update` and `Quick Update` will be available. Select `Normal Update`. 
11. The BIOS will then begin updating. This may take upwards of 5 minutes to complete. 
12. When the update completes, the system will automatically reboot for the changes to take affect. Once the system begins the reboot process, remove the flash drive. 
13. The system should now be up to date.

14. To confirm the update was successful, check in either the BIOS or using `dmidecode` that the BIOS verison is: `F22b Z5`, with a release date of `01/19/2018`. 

**Note:**
After the firmware update completes, if the system reboots with the flashdrive still plugged in, you may be brought to a yellow and black command line prompt titled: "EFI Shell version x". If this is the case, press the `ctrl`-`alt`-`del` keys all at once and your system will restart. Promptly remove the flashdrive and your system will reboot into your operating system.
