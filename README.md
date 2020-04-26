# XDMA_Desc_Bypass_Controller
Descriptor Bypass Controller for Xilinx XDMA IP 

This VHDL code is for a Descriptor Bypass Controller for a XDMA IP from Xilinx. Once the descriptor bypass ports are enabled for the channels in the Vivado Design Suite you can connect the output and input ports to the IP.
Instructions to include the Descriptor Bypass Controller to your block design:

1. Open Xilinx Vivado Design Suite and go to File->Add Sources. Or you can even use the '+' button in the sources window.
2. Check Add or create design sources. Then choose Add Files and import the VHD file and Finish.
3. Right click the VHD file which would appear in the Design Sources/Hierarchy dropdown and select Add module to block design.

The connections between the RTL Module and IP goes as follows:

dsc_byp_ready --> c2h/h2c_dsc_byp_ready_x             (x - Channel number)

dsc_byp_load --> c2h/h2c_dsc_byp_load_x

dsc_byp_length --> c2h/h2c_dsc_byp_len_x

dsc_byp_dst_addr --> c2h/h2c_dsc_byp_dst_addr_x

dsc_byp_src_addr --> c2h/h2c_dsc_byp_src_addr_x

> For Programming instructions and register addresses refer to the Readme file of:  https://github.com/rsarwar87/xdma_dsc_byp_cltr

**NOTE: The Control bit (0x1C) in the Controller Module has to be set only after the Control bit of the H2C/C2H channel (0x04) in the XDMA IP has been set.**

References: https://github.com/rsarwar87/xdma_dsc_byp_cltr
