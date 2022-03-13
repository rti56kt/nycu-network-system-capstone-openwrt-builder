# nycu-network-system-capstone-openwrt-builder

[Spring'22] NYCU CS - Network System Capstone (OpenWrt Image Builder For Edimax BR-6478AC V2)

### Overview

This repo uses the tool named **Image Builder** provided by OpenWrt's official release to quickly generate custom image for Edimax BR-6478AC V2 via GitHub Actions.

### Introduction

Since Edimax BR-6478AC V2 only has 8MB flash and only left ~2.4MB after image flashed, it's hard to install OVS package via opkg service because opkg needs around 3.0MB space to install OVS.

Therefore we need to build our own custom images that OVS packages are built-in.

There are two ways to build OpenWrt image, first is to compile from source code which is more complicated and consumes more time, the second one is to use the Image Builder tool that provided by OpenWrt.

According to [documentation of Image Builder from OpenWrt](https://openwrt.org/docs/guide-user/additional-software/imagebuilder):

> The Image Builder (previously called the Image Generator) is a pre-compiled environment suitable for creating custom images without the need for compiling them from source. It downloads pre-compiled packages and integrates them in a single flashable image.

Appreantly, Image Builder doesn't compile a image, instead, it downloads required packages and files that are pre-compiled and combines them into a image, so it's more simple and time saving.

The only drawback is that it can only add or delete "pre-compiled" packages which means you cannot add a third-party package into the image.

### Author

[Nicholas Li](https://github.com/rti56kt)
