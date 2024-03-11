# TiDE Vehicle Control Unit (VCU)

TiDE main controller built using MATLAB Simulink and Raptor Toolchain.

* [Software Setup Guide](#software-setup-guide)
* [Project Overview](#project-overview)
* [Decoding/Encoding CAN Messages](#decodingencoding-can-messages)
* [Electrical System Block Diagram](#electrical-system-block-diagram)
* [Useful Links](#useful-links)

## Software Setup Guide

See the software setup guide [here](https://docs.google.com/document/d/1cnFTK1jpPUwSgk5_LYbEjfsr6MsOQiAcEhOZyKOdtkA). Please note that all Raptor tools are only compatible with Windows.

For Mac users who wish to view and operate the Raptor software, we recommend using CAEN computers or a Virtual Machine, such as UTM. A guide for running Windows on UTM can be found [here](https://docs.getutm.app/guides/windows/).

## Project Overview

The Vehicle Control Unit (VCU) is essentially the central processing unit of the boat. It activates electrical components, records important data, and controls elements like sensors and actuators. It also serves as the central communication hub between different parts of the boat via the Controller Area Network (CAN) bus, a vehicle bus standard that allows microcontrollers and devices on the boat to communicate with each other without a host computer.

We use the [Raptor General Control Model GCM48](https://store.neweagle.net/shop/raptor/raptor-hardware/raptor-controllers-with-software/raptor-general-control-module-gcm48-2/) as our VCU. Note that you need a New Eagle account (which takes a few business days to get approved) to view the documentation on the New Eagle / New Eagle Wiki site.

The electronic hardware components on our boat (like sensors and actuators) are programmed using software provided by New Eagle. We have free access to New Eagle’s Raptor Toolkit (i.e. Raptor-Dev and Raptor Cal) ($9600 worth of software!) due to our use of the Raptor GCM.

Typically, we would program our electronic hardware using languages like C or Python to implement low-level driver code provided by manufacturers. The Raptor Toolkit simplifies this process, allowing us to use MATLAB Simulink (supplemented with additional Raptor libraries) to program the VCU. Additionally, we use Vector CANalyzer software to program the CAN bus and Kvaser Database Editor to create the DBC files.

## Decoding/Encoding CAN Messages

A CAN DBC file (CAN database) is a text file that contains information for decoding raw CAN bus data to 'physical values'. We use Kvaser Database Editor, which includes the ability to create and edit DBC files, append DBC files, and visualize the signal construction.

Our DBC files are organized in a separate repository: [tide-dbc](https://github.com/uofmelectricboat/tide-dbc). See also the VCU I/O [masterlist](https://docs.google.com/spreadsheets/d/1l9ZZ65pS-U9dvQTbAR1eJ-93yGe8JyaLVBbAq_j7IOM/edit?usp=sharing).

## Electrical System Block Diagram

Below is an image of the current system block diagram (source: [Lucidchart](https://lucid.app/lucidchart/c0bbbfa5-0525-45ad-8ec3-776604d7f318/edit?invitationId=inv_6c9863e5-fb13-4fd6-8d17-4680908d763c&page=0_0#)):

<img src="https://github.com/uofmelectricboat/.github/assets/101139170/32fef8ed-8dbb-4f66-82f4-b4bcb79485ca" alt="drawing" width="350"/>

For more details or access to the Lucidchart file, contact the Electrical Lead.

## Useful Links

* [CAN DBC file explained](https://www.csselectronics.com/pages/can-dbc-file-database-intro)
* [Raw data to decimal converter](https://www.h-schmidt.net/FloatConverter/IEEE754.html)
* [Snowfinkle DBC files](https://github.com/uofmelectricboat/Lightning-McSeas/tree/main/dbc%20files) (Summer 2023 PEP Competition)
