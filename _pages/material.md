---
permalink: /material/
title: Material
header:
  image: /assets/images/feature_image_material.jpg
---

This page provides all material as well as installation instructions for the tools to be used in the tutorial.

## Prerequisites
In order to use the material, there are some prerequisites
* Window/Linux/MacOSX 64bit operating system (amd64 instruction set)
* Java [11;16) installed
* Application to unzip files installed

## Palladio Drop
The Palladio drop is a ready to use Eclipse instance that has all necessary plugins installed. Because the confidentiality extensions are not yet part of the Palladio mainline development, there is a specific drop for the tutorial.

In order to use the drop, you have to
* Download the appropriate version for your operating system
  * [Windows](https://updatesite.palladio-simulator.com/fluidtrust/palladio-bench-product-dataflowconfidentiality/branches/stable/PalladioDataFlowConfidentiality.win32.win32.x86_64.zip)
  * [Linux](https://updatesite.palladio-simulator.com/fluidtrust/palladio-bench-product-dataflowconfidentiality/branches/stable/PalladioDataFlowConfidentiality.linux.gtk.x86_64.zip)
  * [MacOSX](https://updatesite.palladio-simulator.com/fluidtrust/palladio-bench-product-dataflowconfidentiality/branches/stable/PalladioDataFlowConfidentiality.macosx.cocoa.x86_64.zip)
* MacOSX only: [remove quarantine flags](https://sdqweb.ipd.kit.edu/wiki/Palladio_Component_Model/FAQ#MacOS_reports_that_Palladio_is_damaged) by running `xattr -rd com.apple.quarantine Eclipse.app` in the terminal
* extract downloaded drop to any location

## Manual on Using Palladio Drop
We created an [online manual](https://fluidtrust.github.io/tutorial-ecsa2021-tooldoc/) summarizing the most important aspects, which we also explain within the tutorial. The purpose of the manual is mainly to look up aspects, so you are not expected to read the whole manual.

## Task Instructions
The task instructions are available on this website:
* [Modeling Task]({{ site.baseurl }}/tasks/modeling)
* [Analysis Task]({{ site.baseurl }}/tasks/analysis)

## Tutorial Slides
You can download the slides used through the tutorial [here]({{ site.baseurl }}/assets/slides.pdf).