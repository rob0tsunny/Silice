
# Silice example projects

Looking at examples is a great way to learn and experiment. So I prepared several projects, from small to big, to show off Silice features. Some of these projects are still under active development, and evolve together with the language (DooM-chip, I am looking at you!). 

Note that these designs and entirely created from scratch with Silice, from SDRAM, VGA, OLED and LCD controlers to dividers and multipliers, importing only tiny bits of Verilog. Most of the designs rely on common functions grouped in the *common* folder.

To build a design please refer to the [building](#building-a-project) section below and the README of the project.
All designs can be simulated with Icarus/Verilator, and many will work right out of the box on real hardware. Please refer
to the README of each project.

Some projects require a VGA DAC (a bunch of resistors on a breadbord will do!). This is simple and fun to do, so I highly encourage you [to make one](DIYVGA.md).
A few projects rely on some external hardware (typical, low cost things), this is all detailed in the README of the project.

## Building the examples

All examples are in the *projects* directory. This directory also contains a *build* subdirectory, with one entry for each currently supported framework. This includes both simulation (icarus, verilator) and FPGA hardware (icestick, mojo v3, de10nano, etc.).

To build a project, go into projects/build/*architecture* where *architecture* is your target framework. This directory contains shell scripts that take as parameter the project source file. Let's take an example! We will build the 'divint bare' demo for simulation with icarus. Do the following:

*Note:* under Windows please use a MinGW32 shell, please refer to the [getting started](GetStarted.md) guide.

```
cd silice/projects/build/icarus
./icarus_bare.sh ../../projects/divint_bare/main.ice
```
If everthing goes well you should see in the last console output:
```
20043 /   -817 =    -24
```
Yes, the hardware divider is working!

# All examples

## VGA demo effects

Some old-school effects ported on FPGA.

*Tested on*: IceStick, Mojo V3
*Requires*: VGA DAC

## VGA + SDRAM framebuffer demos

### WolfPGA

The (very simplified) render loop of Wolfenstein 3D.

*Tested on*: Mojo V3 + SDRAM (or HDMI) shield
*Requires*: VGA DAC, SDRAM

### The DooM-chip

The DooM-chip, pushing the limits.

*Tested on*: de10-nano with SDRAM board
*Requires*: VGA DAC, SDRAM

## Ice-V

The coolest Risc-V processor (ok, quite an overstatement, but it is a fun project ;) ).

*Tested on*: IceStick
*Optional*: OLED screen

## VGA text buffer

A small demo featuring a font and text buffer

*Requires*: VGA DAC
*Tested on*: IceStick, Mojo V3

## Arithmetic

Divider (because we need one!), multiplier and pipeline multiplier.