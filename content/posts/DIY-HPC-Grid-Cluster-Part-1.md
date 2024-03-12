---
title: "DIY HPC Grid Cluster: Part 1"
date: 2024-03-12T15:40:46+01:00
draft: false
categories: ["Physics", "Computers"]
description: "This article details the process of building a budget-friendly Grid Computing Cluster for theoretical physics simulations. Learn how to repurpose used hardware, install OpenSUSE Leap, configure Slurm workload manager, and leverage OpenMP and MPI libraries for parallel computing. Perfect for students and researchers interested in DIY HPC solutions."
tags: ["DIY Grid Computing Cluster", "Theoretical Physics Simulations", "Parallel Computing with OpenMP and MPI", "Supercomputer on a Budget", "Repurposing Used Hardware for HPC", "Linux Cluster with OpenSUSE Leap", "Slurm Workload Manager", "Theoretical Physics Research"]
---
![](img/supercomputing_grid_cluster_3064264560.png)
## Why

I am interested in Theoretical Physics. However, I can bring many fancy ideas using the Mathematics and Theoretical Laws into new theories, I would waste my time if there is no way to test them. Einstein and his colleagues could come up with calculations that helped test General Relativity. It may not always be the case. With theories becoming more abstract and complicated, and experimental setup getting exorbitant as time passes; I believe, numerical computations and simulations stand to be the first line of defense for further pursued interest in experimental verification of new ideas.

I have spent a great deal of time learning algorithms and solving simple problems using numerical methods. To compute complex mathematical problems requires a great deal of skill and optimization. However, a single piece of computer can only take you so far. One needs to use how to use multiple computers in sync to solve enormous problems that would otherwise be impossible. That is when I realized that I OpenMP and MPI libraries to parallelize the computations.

I can learn theoretical algorithms, but how will I test I am doing the right thing? How can I improve without actually testing my theoretical understanding? I need to execute these algorithms on a Grid Computing Cluster. First bottleneck, I don‘t have access to one. This is where I decided I would build one.

How can I build one? I have experience as Linux System Administrator for 4 years and have basics covered. I need money and some help to build a setup that would be my testing ground. In the next section, let me outline my process to decide upon and acquire the Hardware for such a use case.

## Hardware

All the supercomputers that are built around the globe are based on 2 types of CPU architecture. x86-64 and ARM. So, my testing grounds should have an implementation of both or either of these. ARM is more power efficient, id est, performance to power ratio is high. However, building one for myself that is reasonably performant and cost effective is a factor that outweighs power considerations. My decisions were skewed in favor of x86-64 because of multiple reasons in their decreasing order of preference.

1. Hardware availability and upgradability
2. E-waste reuse
3. Pricing and upgradability
4. Performance
5. Hardware I own prior to deciding upon building one.

There is a lot of used hardware of Mini-PCs or Thin Clients as they are called in the market. Companies buy them in bulk for their employees for usage and upgrade them in a 4-6 year cycle. This means a lot of used but refurbished hardware is available on the market. Upon searching for a perfect CPU and pricing, I decided upon Intel Core i5-6500T based Thin Clients as they price around 100€-120€ based on the configuration. I went with 3 identical units of Fujitsu Esprimo Q556 with 8GB RAM and 250GB SSD in eBay (each unit priced at 88€ only). We have the option to upgrade the RAM and SSD if necessary. I already own an 8-port Gigabit Ethernet switch (by TP-Link) that is unmanaged (no VLANs, or security essentials) and a Beelink MINI S 8G/256G/N5095 PC (which I assigned it as controller node).

The performance of i5-6500T is much faster than N5095 where the latter is a recent release than the former. So, all the Fujitsu Thin Clients turned out to be worker nodes. Terminology clarification: Controller node is the PC that builds the code into binaries, manages queue and users who submit the jobs to compute. Worker nodes are the ones doing heavy-lifting. I also own another Thin Client which I setup as a NAS device serving specific functions. This can serve as a centralized storage pool for data crunching of large files via a NFS share. You will see the messed up wiring and setup of these in the following image.

![](img/20240312_141055.JPG)

Why I didn‘t go for ARM? The options and upgradability are limited, for I can go with multiple Raspberry Pis which is very underperforming and cannot be upgraded later. There is an announcement for Qualcomm‘s own Snapdragon X Elite ARM processor but I would have to wait till its release in June 2024. Even if I wait, I don‘t have any information about the types of hardware that will accompany it. So, due to uncertainty, I decided to drop ARM, even though most new supercomputers use ARM for their power efficiency. I know one can setup a single-node cluster to work with, and I briefly decided to exchange my M1 MacBook Pro for a Mac Mini to do the same since they run on ARM, the support for `slurm` is very limited. So, I waited it out to test my algorithms on ARM when a Thin Client for ARM is released. I could effectively try Microsoft‘s Volterra but support for Linux on that machine is experimental at best.

Fortunately, all the Fujitsu Thin Clients have vPro version of CPUs installed. This means remote management of systems is a breeze. However, the software choice I made has disabled such features.

## Software

The software choice clearly depends on the ability to run `slurm` and utilize maximum compute potential of the worker nodes. The latter forced to decide against Windows and in favor of Linux and BSD. Since I am comfortable with Linux, I am faced with few popular choices: Debian, RHEL or SLES. RHEL is out of my equation since I am not comfortable with the choices IBM has made since it acquired Red Hat. Debian is stable but I just don‘t want to use. That left me with SLES, but I went with OpenSUSE Leap 15.4 since it is open-source version of SLES and is a stable operating system used in many clusters. OpenSUSE has 1:1 binary compatibility with SLES and support for troubleshooting is abundant in the forums. So, I flashed the OS into the USB drive and installed them to all the Thin Clients individually.

OpenSUSE comes in two flavors: Leap and Tumbleweed. The latter is rolling distribution, meaning new software updates every few days that may or may not be stable. The former gets software updates once in a while but they prove to be stable and effective. I don‘t have to convince anyone of the merits of getting stable packages, especially for one who is venturing into this area. We don‘t want to be troubleshooting an incompatible update when we are trying to learn what makes and breaks the algorithms as a novice.

Later I followed documentation of openSUSE and setup `slurmd` and `slurm` packages on the system with `munge` as an authenticator. I also added the controller node, named after Jost Bürgi, for his contributions to the advancement in computing; to a private zero tier network so I can access the controller node from anywhere around the world securely to add a job to compute on my cluster or manage it. The controller node also has a MariaDB server running on it to record all the past job activities and users‘ interactions (will come in handy if I let my friends also play with these toys soon).

## Next Steps

Now I ought to learn OpenMP and MPI libraries and some parallel and distributed computing algorithms before I can think about implementing some simple physics problems to test them. Before that, I intend to benchmark the cluster performance and identify bottlenecks beforehand to know its limitations. The next article I write on this subject will contain this information.

