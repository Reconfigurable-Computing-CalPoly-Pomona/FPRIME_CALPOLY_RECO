# F Prime on the PYNQ-Z1 FPGA Board

### Summary:

NASA has been working on develping a reconfigurable, multi-platform flight software with the intentions of spreading its usability. This is a senior project at **California State Polytechnic University, Pomona** advised by Dr Mohamed El-Hadedy. The purpose of this project is to help the people at JPL port F Prime softwaare onto different types of hardware while benchmarking its performance. The group has been split into two groups. Our group is working with the PYNQ-Z1 FPGA board while the other group is working on a Beagle Bone Black.

### Team Members:

1. Justin Barbour: Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.
2. Keith Chen: Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.
3. Jacky Li: Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.
4. Jimmy Pham: Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.

### Supervising Professor

- **Mohamed El-Hadedy**: Assistant Professor, Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona

### Collaborators

1. **Wen-Mei Hwu**: Director of Center for Cognitive Computing Systems Research and Walter J. Sanders III-AMD Endowed Chair Professor in Elecrical and Computer Engineering at UIUC

2. **Jinjun Xiong**: Director of Center for Cognitive Computing Systems Research and Adjunct Research Professor at UIUC


In order to allow for future expansion of this project as well as popularize the use of F', we are going to show you every step on how to get F' working on a PYNQ-Z1 board.

### Project Reporting

* [Poster](https://github.com/Reconfigurable-Computing-CalPoly-Pomona/FPRIME_CALPOLY_RECO/blob/master/docs/FPrime%20Poster.docx?raw=true)
* [Powerpoint](https://docs.google.com/presentation/d/1cEmyPCkIEoaxFSmNptyelJAsy16G5_C8YAbZ-XLyV8U/edit?usp=sharing)
* [Presentation](https://drive.google.com/file/d/1iBPdokQmRiODfjvTC0dw4HGqXGRs8SN3/view?usp=sharing)

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

## Reference Application

NASA has provided a reference application that can be ran on the Raspberry Pi. The intentions of this application was to help people get familiar with F' tools and terminology.

## Math Component

This tutorial goes through the full development process of an F´ application while letting users see how F' components communicate with each other and how they run. This will create two components. The first components will request the result of a math problem. The second component will do the math and comupte the answer. This does not actually need embedded devices or hardware. Instead, it runs only off of the user's .nix system (Linux, MacOs, Windows, BSD). Make sure to complete the reference application tutorial above because that application acts as a host for the components.


## Licenses and Copyrights

**PYNQ** License: [BSD 3 Clause License](https://github.com/Xilinx/PYNQ/blob/master/LICENSE)

**Xilinx Embedded Software** License: [Multiple License File](https://github.com/Xilinx/embeddedsw/blob/master/license.txt)

**Digilent IP** License: [MIT License](https://github.com/Xilinx/PYNQ/blob/master/THIRD_PARTY_LIC) 

Copyright (c) 2009-2019, California Institute of Technology ("Caltech"). U.S. Government sponsorship acknowledged.

All rights reserved.
