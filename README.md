# F Prime on the PYNQ-Z1 FPGA Board

### Summary:

NASA has been working on develping a reconfigurable, multi-platform flight software with the intentions of spreading its usability. This is a senior project at **California State Polytechnic University, Pomona** advised by Dr. Mohamed El-Hadedy. The purpose of this project is to help the people at JPL port F Prime software onto different types of hardware while benchmarking its performance. The team has been split into two groups. Our group is working with the PYNQ-Z1 FPGA board while the other group is working on a Beagle Bone Black. Our page is set up to not only display our work and results, but to also be set up as a tutorial to allow for others to implement F' on their own and to allow for future expansion on this project.

### Team Members:

1. Justin Barbour: Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.
2. Keith Chen: Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.
3. Jacky Li: Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.
4. Jimmy Pham: Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.

### Supervising Professor

- **Mohamed El-Hadedy**: Assistant Professor, Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.

### Collaborators

1. **Wen-Mei Hwu**: Director of Center for Cognitive Computing Systems Research and Walter J. Sanders III-AMD Endowed Chair Professor in Elecrical and Computer Engineering at UIUC

2. **Jinjun Xiong**: Director of Center for Cognitive Computing Systems Research and Adjunct Research Professor at UIUC

### Project Reporting

* [Poster](https://github.com/Reconfigurable-Computing-CalPoly-Pomona/FPRIME_CALPOLY_RECO/blob/master/docs/FPrime%20Poster.docx?raw=true)
* [Powerpoint](https://docs.google.com/presentation/d/1cEmyPCkIEoaxFSmNptyelJAsy16G5_C8YAbZ-XLyV8U/edit?usp=sharing)
* [Presentation](https://drive.google.com/file/d/1iBPdokQmRiODfjvTC0dw4HGqXGRs8SN3/view?usp=sharing)

### Beagle Bone Black Team

Here is a link to our [Beagle Bone Black Team](https://github.com/Reconfigurable-Computing-CalPoly-Pomona/Fprime-CalPoly).

# Getting Started

In order to run F' on the PYNQ-Z1, there were a few prerequisites that needed to be taken care of. This included having the proper hardware with the proper software downloaded and installed.

## Hardware and Software Requirements

To run F', it is necessary to have a:
- PYNQ-Z1 FPGA Board
- Computer the runs Linux, MacOs, or Windows with PuTTY installed
- Micro SD Card (minimum 8GB required)

## Setting Up the Board

In order to run F' on the PYNQ-Z1 board, we need to download and write a bootable image to a micro SD card and then boot the board from that micro SD card.

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

## Installation of F' and Running the Reference Application

F´ requires that the following utilities be installed: cmake, git, and Python 3 with pip. 

It is also recommended to install F' Python dependencies.

Our [Installation Guide](https://github.com/Reconfigurable-Computing-CalPoly-Pomona/FPRIME_CALPOLY_RECO/blob/master/fprime_pynq_installation_guide.txt) contains the steps and code needed in order to install the utilities mentioned above as well as how to install FPrime and run the reference application.

The intentions of the reference application was to help people get familiar with F' tools and terminology.

### F' Component Build Processes

The following flow charts are to help visualize the building processes of an F Prime Component.

<p align="center"> <img width="821" alt="Screen Shot 2020-04-29 at 7 07 12 PM" src="https://user-images.githubusercontent.com/57409161/80666687-dcd2ad80-8a51-11ea-9d5c-e48ddcd98f1f.png">
<p align="center"> Fig.1 Component Build
  
<p align="center"> <img width="696" alt="Screen Shot 2020-04-29 at 7 07 28 PM" src="https://user-images.githubusercontent.com/57409161/80667520-3936cc80-8a54-11ea-8b0c-de0bce941520.png">
<p align="center"> Fig.2 F Prime-Util

## Math Component

Our [Math Component Tutorial](https://github.com/Reconfigurable-Computing-CalPoly-Pomona/FPRIME_CALPOLY_RECO/blob/master/MathComponentTutorial.txt) goes through the full development process of an F´ application while letting users see how F' components communicate with each other and how they run. This will create two components. The first components will request the result of a math problem. The second component will do the math and compute the answer. This does not actually need embedded devices or hardware. Instead, it runs only off of the user's .nix system (Linux, MacOs, Windows, BSD). It is necessary to complete the reference application because that application acts as a host for the components.

## Math Component Benchmarks

We created a program to monitor the performance of the PYNQ-Z1 board while running the math component in comparison to our other group that was running it on the Beagle Bone Black. Both of these boards are running identical math functions.

### Performance on the PYNQ-Z1:
<p align="center"> <img width="323" alt="Benchmark" src="https://user-images.githubusercontent.com/57409161/80663964-549cda00-8a4a-11ea-98b9-dbef05ec4324.png">

### Performance on the Beagle Bone Black:
<p align="center"> <img width="284" alt="BenchmarkBBB" src="https://user-images.githubusercontent.com/57409161/80664357-68950b80-8a4b-11ea-9dec-d283a87ab7b4.png">

As seen above, the PYNQ has far better performance due to it having a Dual-Core 650 MHz Cortex-A9 ARM Processor
as opposed to the Beagle Bone that only has a single-core AM3358 1Ghz ARM Cortex-A8 processor. Because of the dual-core processor, our CPU will use a max of 95% but averages at around 47%. The single-core on the BBB maxes out at 100% and averages around 82%.

## Future Work
Although the reference application and math components were successfully implemented on the PYNQ-Z1 FPGA board, there is still future work to accomplish. NASA has provided a GPS module for us to implement on our board and test its performance. We are also working on creating our own custom boot image. This image will allow for more customizability, better optimization, and better performance than the PYNQ Image used previously. Our page was also specifically set up in hopes to allow for future expansion of this project by other teams, providing the ground work on how to install and run F' on the PYNQ-Z1. 

## Sponsors

[Xilinx](https://www.xilinx.com/)

[IBM](https://www.ibm.com/)

[IBM-Illinois Center for Cognitive Computing System Research](https://www.c3sr.com/)

[PYNQ BSD 3 Clause License](https://github.com/Xilinx/PYNQ/blob/master/LICENSE)

[Digilent IP MIT License](https://github.com/Xilinx/PYNQ/blob/master/THIRD_PARTY_LIC) 

Copyright (c) 2009-2019, California Institute of Technology ("Caltech"). U.S. Government sponsorship acknowledged.

All rights reserved.
