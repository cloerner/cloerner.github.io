---
title: "64GB in an Intel NUC7i3"
date: 2019-09-26T08:22:30+02:00
draft: false
---

Memory in the homelab. A topic that probably hits everyone. Most of the time CPU resources are sufficient, but memory is usually a bottleneck.
My colleague William Lam has tested the new 32GB Dimms in his Intel NUCs. [Link](https://www.virtuallyghetto.com/2019/03/64gb-memory-on-the-intel-nucs.html). Unfortunately, William has no generation 7 NUCs.
So I thought, take the 300 Euros and test it yourself in your environment. I ordered the new dimms [here](https://www.future-x.de/samsung-speichermodul-32-gb-ddr4-2666-mhz-sodimm-2r-x-8-2g-x-8-x-16-12-v-p-4441646/).
The installation was super easy and after 10 minutes the new memory was installed. Since you have shutdown your host for the installation, I decided to upgrade the bios to the last version.
And guess what: My ESXi 6.7U3 recognizes the memory and now runs with 64GB. My two other NUCs will also be equipped with the new dimms, which ends up in 192GB of memory for my homelab. That should be enough for the next time.
![](/images/nuc64.png)
