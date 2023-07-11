---
title: "Why Mac Studio Is the Cheapest Hardware"
date: 2023-07-11T11:08:41+02:00
draft: false
categories: ["Computers"]
description: "The backstory involves an individual working on a project that requires the use of AI models with high system resource demands. Traditional hardware falls short in terms of memory capacity, so the individual explores the option of utilizing multiple GPUs like the NVIDIA A100 Tensor Core-GPU to achieve the necessary memory. However, due to budget and resource constraints, they are unable to develop a prototype. A fully speced out Comino grando Liquid-cooled multi-GPU workstation/server is estimated to cost at least $38,700, excluding additional expenses such as electricity and networking costs. Alternatively, the individual considers using a Mac Studio, which is more cost-effective and energy-efficient. However, turning it into a server requires addressing issues such as the preinstalled desktop operating system and the need for a downstream OS with stability and security."
tags: ["Apple", "Server", "Technology", "Linux"]
---

![](img/mac-studio.png)

## Backstory

I started working on a project on my free time to cater to curiosity. This project requires extensive use of AI Models that happens to utilize huge system resources. The details of the project's scope are not in my authority to discuss here. Traditionally, AI models are trained and run on GPUs or TPUs which contain VRAM memory to process the data. Consumer hardwares from NVIDIA and AMD Systems have a maximum of 24 GB of VRAM memory and commerical ones from NVIDIA have around 80 GB. However, the models I have in use require 90+ GB of memory. The model I have in mind is Falcon-70B-instruct. How is it achieved? Utilize multiple GPUs like NVIDIA A100 Tensor Core-GPU. In this case 2 units that give us barely 160 GB of memory. It ain't a plug-and-play solution either. There are methods like model quantization and other software development techniques to utilize multiple hardware to execue such AI Models. 

I neither have the budget nor the resources to test these to develop a prototype of my project. But how much would the budject be to deploy such a solution?

## Budgeting

In the far future, the hardware requirements would be close to a speced out Comino grando Liquid-cooled multi-gpu workstation / server. An estimate of cost for the totally speced out version would cost:

| Component              | Cost    |
|------------------------|---------|
| CPU x2                 | $16000  |
| GPU x4                 | $20800  |
| RAM                    | $1900   |
| Overall Minimum Budget | $38700+ |

38700 USD just for server. Electricty costs and networking costs will pile up. In enterprise setting, this ain't costly.

## Enter Mac Studio

The AI tools like Pytorch and Tensorflow are constantly optimized for ARM processors of Apple Devices. A fully speced out MAc Studio costs $8800 only. The one I  might require only costs $6700. Now that is one order of magniture reduction of costs. Not to mention the power efficiency of the machine, the costs of running a server is saved multifold. The power consumption of Mac Studio is 370 Watts only. Whereas the Linux Server from Comino is around 2.5kW. So, Mac Studio as a server is very cost effective and climate friendly.

## Issues

Mac Studio comes preinstalled with MacOS Ventura or Sonoma which is a desktop OS. To turn it into server, we can use NGINX or Apache and deploy the software we wish to use. However, the Graphical User Interface and other Mac related applications would also run in the background thus limiting the performance potential of the hardware. One solution is to install Asahi Linux which is an Arch-based distro specific to Apple Silicon Macs. However, Arch-based systems are upstream and have unstable packages and still requires heavy development. To host server, one needs a downstream OS with stability and security batte-tested.