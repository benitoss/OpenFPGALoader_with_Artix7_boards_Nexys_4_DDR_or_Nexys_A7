# Use OpenFPGALoader with Artix7 boards (Nexys 4 DDR or Nexys A7)
Use OpenFPGALoader to program an FPGA locally or remotely in Vivado or ISE IDE in Linux or Windows

This repository explains how to use OpenFPGALoader to program a board directly or remotely in Linux or Windows

# JTAG Programmer for Nexys 4 DDR or Nexys A7

The JTAG programmer contained in both Nexys boards is compatible with an FT2322 programmer.

# Install LibUSBK to work in Windows (Linux users don't need this part)

When working in Windows, you have to install the LibUSBk driver so that OpenFPGASoftware recognizes the JTAG programmer.

I use the utility USB Driver Tool; you can download it from https://visualgdb.com/UsbDriverTool/  
The latest version is here --> https://sysprogs.com/getfile/1372/UsbDriverTool-2.1.exe

For FT2232H JTAG programmer or a compatible device, you will see the "USB Serial Converter A" with VID 0403 and VPI 6010.

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/USB_Driver_Tool_1.jpg)

So, you have to press the right mouse button over it and select "Install Libusb-WinUSB"

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/USB_Driver_Tool_2.jpg)

You will see the line "USB Serial Converter A" and in parentheses, Libusb-WinUSB. Now, you have the drivers already installed for OpenFPGALoader.

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/USB_Driver_Tool_3.jpg)

## Download the OpenFPGALoader software 

For Windows, you can download the Windows executable Version from [here](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/raw/refs/heads/main/OpenFGPALoader/openFPGALoader_V1.1.1_Windows_with_XVC_20260828.zip).

For Linux, go to the OpenFPGALoader repository page [here](https://github.com/trabucayre/openFPGALoader) and install the software. 

You have two options to program the FPGA board.
1) Program the board directly with the bitstream file (bit file) from the terminal
2) Program the board remotely from a Vivado running on another PC or Device (Example: Citrix)

For both options, you have to open a CMD in Windows or a shell terminal in Linux

Go to the Windows Search menu (on the bottom bar) and type CMD. You will see a window and the application "Command Prompt"; click " Run as administrator " on the right side.

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/cmd_1.jpg)

## 1. Program the board directly with the bitstream file (bit file) from the terminal 

**Important:** Turn on your FPGA Board

Type in the CMD terminal "openFPGALoader.exe -b nexys_a7_100 --detect".
You should see a screenshot like this:

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/openFPGALoader_1.jpg)

This means that the FPGA board is recognized by the OpenFPGALoader application and is working

To program the FPGA board with the bit file, we type "openFPGALoader.exe -b bitfile.bit".

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/openFPGALoader_2.jpg)

Fantastic !!! We have already programmed our FPGA board.

## 2. Program the board remotely from a Vivado running on another PC or Device (Example: Citrix) 

In this case, you will activate the XVC (Xilinx Virtual Cable) Server on your computer.

**Important:** Because you are going to run a server on you PC, you need to open a port in the Router to be visible from outside of your local network.
           You have more information [here](https://share.google/aimode/z2rcQWRW5NuqTHSj8) 
           
Type in the CMD terminal "openFPGALoader.exe -b nexys_a7_100 --xvc --port 8000". (You can change the port number)
You should see a screenshot like this:

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/openFPGALoader_XVC.jpg)

**Do not close this CMD terminal window; leave it open!!!**

You need to know the public IP address that the ISP is giving to your router.

The easy way is to visit the webpage --> https://whatismyipaddress.com/

Get the IPV4 address. The IP Address is written in dotted-decimal notation as four numbers separated by periods (e.g., 65.168.1.1).

**Remember:** You should activate the port forwarding in your router for port 8000 to the local IP of your PC where you are running the XVC Server.

Now, open Vivado IDE on a remote computer (or Citrix)

Once you have selected "Open Hardware Manager", click on "Open target" and then on "Auto Connect"

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/Vivado_2.jpg)

You will see "localhost(0)"; right-click it and click on "Add Xilinx Virtual Cable (XVC)"

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/Vivado_3.jpg)

You should see a screenshot like this:

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/Vivado_4.jpg)

Introduce the IP of the Server that you got before, and the port that you selected before too (8000, for example), and press the OK button.

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/Vivado_5.jpg)

In yellow, you will see the IP address and port of the XVC server.
The FPGA is recognized as xc7a100t_0(t)

Right-click on "xc7a100t_0(t)" and click on "Program Device..."

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/Vivado_6.jpg)

In the Bitstream file, you will usually see the bitstream already selected

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/Vivado_7.jpg)

Press the Program button

Congratulations !!!!
The FPGA board will be programmed remotely with the selected bitstream
