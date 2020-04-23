# F Prime on the PYNQ-Z1 FPGA Board

### Summary:

NASA has been working on develping a reconfigurable, multi-platform flight software with the intentions of spreading its usability. This is a senior project at **California State Polytechnic University, Pomona** advised by Dr Mohamed El-Hadedy. The purpose of this project is to help the people at JPL port F Prime softwaare onto different types of hardware while benchmarking its performance. The group has been split into two groups. Our group is working with the PYNQ-Z1 FPGA board while the other group is working on a Beagle Bone Black.

In order to allow for future expansion of this project as well as popularize the use of F', we are going to show you every step on how to get F' working on a PYNQ-Z1 board.

# Tutorial

The following is going to be a complete tutorial for installing anf running F' on a PYNQ-Z1 board.

## Hardware and Software Requirements

To run F', you are going to need a:
- PYNQ-Z1 FPGA Board
- Computer the runs Linux, MacOs, or Windows with PuTTY installed
- Micro SD Card (minimum 8GB required)

F´ requires that the following utilities be installed: cmake, git, and Python 3 with pip. 

It is also recommended to install F' Python dependencies.

If using MacOs, I reccomend installing HomeBrew in order to have all of the missing files and commands found in Linux.

## Setting Up the Board

In order to run F' on the PYNQ-Z1 board, you need to download and write a bootable image to a micro SD card and then boot the board from that micro SD card.

### Downloading the Bootable Image

First you need to download the [PYNQ-Z1 Image](http://files.digilent.com/Products/PYNQ/pynq_z1_v2.1.img.zip)

If the download does not start, you can download it directly from [Xilinx's Page](https://github.com/xilinx/PYNQ/blob/v2.2.1/docs/source/getting_started/pynq_image.rst#id2)

### Writing the Image to the SD Card

In order to write the image to the SD card, you need to :
1. Download the image provided above
2. Unzip the files
3. Write the image to a **BLANK** SD Card

For a more detailed version of writing the image, you can follow this [tutorial](https://pynq.readthedocs.io/en/v2.2.1/appendix.html#writing-the-sd-card) that was provided

### Board Setup

Once you have the image downloaded, the board must get set up in order to properly run. 
You can follow the quick installation guide provided by Xilinx [here](https://pynq.readthedocs.io/en/latest/getting_started/pynq_z1_setup.html)

## Quick Installation of F'

There is a [full installation guide](https://github.com/nasa/fprime/blob/master/docs/INSTALL.md) that can be found on [NASA's F Prime Page](https://github.com/nasa/fprime), but below is the most basic steps for convenience.

```
git clone https://github.com/nasa/fprime.git
cd fprime
pip install Fw/Python Gds/
```



## Licenses and Copyrights

**PYNQ** License: [BSD 3 Clause License](https://github.com/Xilinx/PYNQ/blob/master/LICENSE)
**Xilinx Embedded Software** License: [Multiple License File](https://github.com/Xilinx/embeddedsw/blob/master/license.txt)
**Digilent IP** License: [MIT License](https://github.com/Xilinx/PYNQ/blob/master/THIRD_PARTY_LIC) 

