---
title: "64GB in an Intel NUC7i3"
date: 2019-09-26T08:22:30+02:00
draft: false
tags:
- homelab
- Intel NUCs
---

Memory in the homelab. A topic that probably hits everyone. Most of the time CPU resources are sufficient, but memory is usually a bottleneck.
My colleague William Lam has tested the new 32GB DIMMs in his Intel NUCs. <a href="https://www.virtuallyghetto.com/2019/03/64gb-memory-on-the-intel-nucs.html" target="_blank">Link</a>


Unfortunately, William has no generation 7 NUCs.
So I thought, take the 300 Euros and test it myself in my environment. I ordered the new DIMMs <a href="https://www.future-x.de/samsung-speichermodul-32-gb-ddr4-2666-mhz-sodimm-2r-x-8-2g-x-8-x-16-12-v-p-4441646/" target="_blank">here.</a>


The installation was super easy and after 10 minutes the new memory was installed. Since you have to shutdown your host for the installation, I decided to upgrade the bios to the last version.
And guess what: My ESXi 6.7U3 recognizes the memory and now runs with 64GB. My two other NUCs will also be equipped with the new DIMMs, which ends up in 192GB of memory for my homelab. That should be enough for now.

---
![](/images/nuc64.png)
