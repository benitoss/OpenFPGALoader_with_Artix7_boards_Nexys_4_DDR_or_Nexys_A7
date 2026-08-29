# Use OpenFPGALoader with Artix7 boards (Nexys 4 DDR or Nexys A7)
Use OpenFPGALoader to program an FPGA locally or remotely in Vivado or ISE IDE in Linux or Windows

This repository explains how to use OpenFPGALoader to program a board directly or remotely in Linux or Windows

# JTAG Programmer for Nexys 4 DDR or Nexys A7

The JTAG programmer contained in both Nexys boards is compatible with an FT2322 programmer.

# Install LibUSBK to work in Windows (Linux users don't need this part)

When working in Windows, you have to install the LibUSBk driver so that OpenFPGASoftware recognizes the JTAG programmer.

I use the utility USB Driver Tool; you can download it from https://visualgdb.com/UsbDriverTool/  
The latest version is here --> https://sysprogs.com/getfile/1372/UsbDriverTool-2.1.exe
If you use the FT2232H JTAG programmer or a compatible device, you will see the "USB Serial Converter A" with VID 0403 and VPI 6010.

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/USB_Driver_Tool_1.jpg)

So, you have to press the right mouse button over it and select "Install Libusb-WinUSB"

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/USB_Driver_Tool_2.jpg)

You will see the line "USB Serial Converter A" and in parentheses, Libusb-WinUSB. Now, you have the drivers already installed for OpenFPGALoader.

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/USB_Driver_Tool_3.jpg)

## Download the OpenFPGALoader software 

For Windows, you can download the Windows executable Version from [here](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/raw/refs/heads/main/OpenFGPALoader/openFPGALoader_V1.1.1_Windows_with_XVC_20260828.zip)
For Linux, go to the OpenFPGALoader repository page [here](https://github.com/trabucayre/openFPGALoader) and install the software 

## Program the bitstream (bit file) directly

- Colorlight 5A-75B
- Colorlight 5A-75F
- Colorlight i5
- IceSugar Pro 


