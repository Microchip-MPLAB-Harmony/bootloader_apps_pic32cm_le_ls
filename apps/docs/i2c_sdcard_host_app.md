---
grand_parent: UART-I2C Factory Programmed Bootloader Applications
parent: UART-I2C Factory Programmed Bootloader
title: Building and Running on SAM E54 Xplained Pro Evaluation Kit
has_toc: false
---

[![MCHP](https://www.microchip.com/ResourcePackages/Microchip/assets/dist/images/logo.png)](https://www.microchip.com)

### **Using I2C SDCARD Host application to send the application binary to Target development kit**

![host_app_sdcard_setup](images/i2c_bootloader_host_sdcard.png)

1. Open the SDCARD host application project *bootloader_apps_pic32cm_le_ls/apps/i2c_host_app_sdcard/firmware/sam_e54_xpro.X* in the IDE

2. Build and program the SDCARD host application using the IDE on to the I2C host dvelopment kit. Make sure the correct target board is defined by defining the *APP_I2C_BOOTLOADER_TARGET_DEVICE* macro to the appropriate value in the user.h file.

3. Build and generate the application binary to be bootloaded. Follow the steps outlined under [Application project configurations for CORTEX-M based MCUs](https://microchip-mplab-harmony.github.io/bootloader/?GUID-74A00B0A-18C1-47BD-A5F7-5BAFEDDAD130)

4. Copy the application binary generated in step 3, into the SD card and insert the SD card in the SD card slot available on the [SAM E54 Xplained Pro Evaluation Kit](https://www.microchip.com/developmenttools/ProductDetails/atsame54-xpro) 

5. Open the Terminal application (Ex.:Tera Term) on the computer

6. Configure the serial port settings for **Host Development kit** as follows:
    - Baud : 115200
    - Data : 8 Bits
    - Parity : None
    - Stop : 1 Bit
    - Flow Control : None

7. Press the Switch **SW0** on the Host development kit to trigger programming of the application binary

8. Once the programming is complete,
    - **LED0** on the Host development kit will be turned on indicating success

    - Following message will be displayed on the terminal of **Host development kit**

        ![i2c_bootloader_host_app_sdcard_output](images/i2c_bootloader_host_app_sdcard_output.png)

    - The target will be reset. Upon re-start, the boot-loader will jump to the user application    