# Use OpenFPGALoader with Artix7 boards in windows
Use OpenFPGALoader to program an FPGA locally or remotely in Vivado or ISE IDE in Windows

This repository explains how to use OpenFPGALoader to program a board directly or remotely in windows

# JTAG Programmer for Nexys 4 DDR or Nexys A7

The JTAG programmer contained in both boards is compatible with an FT2322 programmer.

# Install LibUSBK to work in Windows (Linux users don't need this part)

When working in Windows, you have to install the LibUSBk driver so that OpenFPGASoftware recognizes the JTAG programmer.

I use the utility USB Driver Tool; you can download it from https://visualgdb.com/UsbDriverTool/  
The last version is here --> https://sysprogs.com/getfile/1372/UsbDriverTool-2.1.exe
If you use the FT2232H JTAG programmer or a compatible device, you will see the "USB Serial Converter A" with VID 0403 and VPI 6010.


## Program the bitstream (bit file) directly

- Colorlight 5A-75B
- Colorlight 5A-75F
- Colorlight i5
- IceSugar Pro 


