---
layout: post
title: "WSL2 USB Devices"
author: "Malek Atwiz"
---

Steps to access USB devices in WSL2:

Assuming you have WSL2 installed and set up, follow these steps to access USB devices:

1. **Install USBIPD**:
   Open PowerShell as Administrator and run:

   ```powershell
   wsl --install -d usbipd
   ```

   or follow the manual installation steps from the [USBIPD-WIN GitHub repository](https://github.com/dorssel/usbipd-win?tab=readme-ov-file#usbipd-win).

2. **Start USBIPD**:
   After installation, list available USB devices:

   ```powershell
   usbipd list
   ```

   you should see a list of USB devices connected to your Windows machine.

3. **Bind USB Device**:
   If you want to bind a specific USB device to WSL2, you can use the following command:

   ```powershell
    usbipd bind --busid <busid>
    ```

4. **Attach USB Device**:
   To attach a USB device to WSL2, use the following command:

    ```powershell
    usbipd attach --busid <busid>
    ```

   Replace `<busid>` with the bus ID of the USB device you want to attach, which you can find from the previous `usbipd list` command.

5. **Access USB Device in WSL2**:
   Open your WSL2 terminal and check if the device is available. You can use commands like `lsusb` to list USB devices:

   ```bash
   lsusb
   ```

   If the device is attached successfully, it should appear in the list.
