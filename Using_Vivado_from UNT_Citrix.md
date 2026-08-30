# Start Vivado from UNT Citrix

Go to this [page](https://academictechnologies.unt.edu/services/computer-labs/request/remotely-connect-mylab-virtual-computer-lab)
Go to Step 2 and click on "Connect using Citrix Workspace -->" 

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/Citrix_1.jpg)

You will need to log in as a UNT student with two-factor authentication.

Search for the Vivado 20252 Application and click on it.

# Download the bitfile from Vivado (Citrix)

Go to the upper menu and click on "File Transfer", and then click on "Download"

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/Citrix_2.jpg)

Select the bit file of the project; usually for the project "example_1", it is in the subfolder "/example_1.runs/impl_1/"  and the file stream is called "example1.bit"

![alt text](https://github.com/benitoss/Use_OpenFPGALoader_as_XVC_server/blob/main/images/Citrix_3.jpg)


# Program the board remotely from a Vivado running on Citrix

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
