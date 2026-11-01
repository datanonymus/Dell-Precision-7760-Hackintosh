[Chuyển sang hướng dẫn bằng tiếng Việt tại đây!]()

# 📖 Detailed Installation Guide

### 🛠 Prerequisites
1. A USB drive (at least 1GB) to hold OpenCore and the macOS Recovery image.
2. A Brain 🐔!

### ⚙️ Step-by-Step Instructions

**Step 1:** Boot into Windows -> Open `Disk Management` -> Shrink your disk to create a partition of at least 50GB and format it as NTFS.

**Step 2:** Format your USB drive. It **MUST** be in `FAT32` format.

**Step 3:** Go to the GitHub page containing the EFI source, click `Code` -> `Download Zip`. Extract the contents to your USB. Ensure that the `EFI` folder is at the root of the USB drive.

**Step 4:** Go to [this Google Drive link](https://drive.google.com/drive/folders/1jF8dr618N80z5FbvR1IqrAyxI52rl60N) and download the macOS Tahoe recovery image. Copy the `com.apple.recovery.boot` folder to the root of your USB drive, right next to the `EFI` folder.

**Step 5:** Open your browser, go to [OCAuxiliaryTools Releases](https://github.com/ic005k/OCAuxiliaryTools/releases), and download `OCAT-Win64.zip`. Extract it, find `OCAT.exe`, and run it.

**Step 6:** In OCAT, click `File` -> `Open` -> Navigate to your USB -> `EFI` -> `OC` -> select `config.plist` and open it.

**Step 7:** Go to the `PI` tab. Next to `SystemProductName`, click the **Generate** button to create new SMBIOS device information. Press `Ctrl + S` to save the configuration.

**Step 8:** Restart your laptop. Press `F2` continuously to enter the BIOS and apply these settings:

- **Advanced Optimus / Hybrid Card:** OFF
- **Secure Boot:** OFF

**Step 9:** Save and exit BIOS. During the reboot, press `F12` continuously to enter the Boot Options menu. Use your mouse/keyboard to select your USB drive.

**Step 10:** Once the OpenCore menu appears, scroll down, select the option with the word `Recovery`, and press Enter to boot into the macOS installer.

**Step 11:** Once booted, you will likely see an interface entirely in Russian (Well... I don't know why 🤷‍♂️! Blame Apple =))!). Click the second option from the Apple logo on the top right corner, then change the language to your preference.

**Step 12:** Open `Disk Utility` -> Click `View` -> Select `Show all devices`. Locate the 50GB partition you prepared earlier. Click `Erase` -> Name it and format it as **APFS** -> Click `Erase` again to format it to the macOS standard.

**Step 13:** Close Disk Utility. Select `Install macOS Tahoe 26`. **Note:** Plug in an Ethernet cable so the Recovery can download the full OS, or if you're lucky, the Wi-Fi kext might just work! (Well... idk 🤔. Test it yourself! 🤷‍♂️). Click Next. Select the APFS partition you just created and click Next to start installing.

**Step 14:** Go make a pot of tea 🗿! Come back in about an hour =)))!

**Step 15:** After downloading and installing, the machine will auto-reboot. You will now see an `Installer (ext)` option. Select it. The laptop will reboot 2 or 3 more times. Keep selecting the `Installer` option until you finally see the `macOS Tahoe 26` (your main drive name) option. *(Pro tip: If it gets stuck for way too long at any stage—like 2 hours... maybe 🤷‍♂️—just hold the power button for 10 seconds to force shutdown, turn it back on, and it should be fine!)*.

**Step 16:** Once you reach the macOS desktop and finish the setup (don't panic, there's no graphics acceleration yet, so it will lag like crazy 🐔!), open Safari. Go to [nullMoth's NVIDIA macOS driver repo](https://github.com/nullmoth/nvidia-macos-driver) and download the latest `.dmg`. Open it, skip the warning. Go to `System Settings` -> `Privacy & Security` -> Scroll down to find the warning blocking app `1401` -> Click `Open Anyway` -> Enter your password to open the app.

**Step 17:** In the app, you'll see 4 steps corresponding to 4 buttons. Click them in order: `Download` -> `Show me the changes` -> `Install driver`. Each step takes some time, so be patient!

**Step 18:** When the `Restart Now` button lights up, go back to `System Settings` -> `Privacy & Security` -> Scroll down to where you allowed the app earlier -> Click the `Review` (or Allow) button for new extensions -> Click `Done`.

**Step 19:** Open Safari, go back to [OCAuxiliaryTools Releases](https://github.com/ic005k/OCAuxiliaryTools/releases), and download the latest `OCAT_Mac.dmg`. Follow the same Privacy bypass steps (like in Step 16) to open OCAT.

**Step 20:** In OCAT, click `File` -> `Open`, navigate to your USB -> `EFI` -> `OC` -> open `config.plist`.

**Step 21:** Go to the `NVRAM` section -> `Add` tab -> select the `7C436110-AB2A-4BBB-A880-FE41995C9F82` UUID -> Double-click the value box next to `boot-args` and **delete** the `-nvoff` flag at the end -> Press `Cmd + S` (or click Save).

**Step 22:** Go back to app `1401` and click `Restart Now`.

**Step 23:** On reboot, select `macOS Tahoe 26` and enjoy Metal 3 acceleration!

### 🚀 Post-Install: Booting Without the USB

**Step 1:** In macOS, download the `Hackintool` app. Bypass security to open it just like before.

**Step 2:** Go to the `Disk` tab -> Look at the `EFI Partitions` section -> Find the disk containing your Windows installation -> Click the `Mount` icon -> Enter your password. It will mount under the name `NO NAME`.

**Step 3:** Open your USB drive and copy the entire `OC` folder. Then open the `NO NAME` drive -> `EFI` folder -> paste the `OC` folder here.

**Step 4:** Go back to your USB drive -> `EFI` -> `BOOT` -> copy the `BOOTx64.efi` file. Then open the `NO NAME` drive -> `EFI` -> `Boot` -> rename the existing file to `Bootx64.efi.bak` and paste your copied `BOOTx64.efi` file.

**Step 5:** Restart your laptop. Press `F2` to enter BIOS. Go to `Boot Configuration` -> Click `Add Boot Option`. In the `Browser File` section, navigate through your `NO NAME` EFI partition until you see the structure -> Open the `Boot` folder -> Select the `BOOTx64.efi` file -> Name it `OpenCore` -> Click Save -> Click `Apply Changes`. Move the `OpenCore` option to the top of the boot priority list -> Click `Apply Changes` again. 

**Step 6:** Exit, reboot, and enjoy! 🗿
