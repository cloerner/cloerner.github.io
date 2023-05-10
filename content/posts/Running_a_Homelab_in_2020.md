---
title: "Running a Homelab in 2020"
date: 2020-01-24T08:22:30+02:00
draft: false
tags:
- homelab
- Intel NUCs
---

Why running a Homelab? You need time, you need money and you need electrical power. But where else can you test new software or new features? The cloud could be
a good way. But clouds are often expensive, and I wanted to have my lab on-premises.


There are two ways to build a Homelab on your own. You can buy a big server and test the software in a nested kind of way, or you can buy two or more small form factor (SFF) servers to get the full "native" experience.

Regarding “Nested Virtualization”, I´d recommend having a closer look on the articles my well appreciated <a target="_blank" href="https://www.virtuallyghetto.com/nested-virtualization">colleague William Lam has written.</a>

Running a rackmount server like an HPE ProLoant DL380 GEN 10 server for example, means to be aware of a few operational drawbacks, such as power consumption, heat and noise.


I decided to go with the SFF:
![](/images/BOM.png)

My hardware setup has an electrical footprint of ~200 watts, which makes running the Homelab 24*7 acceptable.

My bill of materials (BOM):

| Part                  | Quantity |  Single Price| Price |
|-----------------------|:--------:|:------------:|------:|
| Intel NUC NUC7I3BNH   | 3        | $265         | $795  |
| Memory Kit 2x16GB     | 3        | $331         | $993  |
| Samsung 850 EVO M.2   | 3        | $175         | $525  |
| Seagate Baracuda 2TB  | 3        | $95          | $285  |
| Synology DS415+       | 1        | $1100        | $1100 |
| USB 3 Network Adapter | 6        | $15          | $90   |
| TP-LINK GB Switch     | 1        | $100         | $100  |
|                       |          |              |       |
|                       |          | Sum:         | $3988 |


I started with 2x16GB of memory per host, because 32GB memory DIMMs were not affordable in the period of procurement. But after a year, I decided to upgrade the memory to 64GB per Host, which
costs me additional $1000. I know…expensive! But a necessary evil.

Now I am able to run many solutions from VMware/Pivotal in my Homelab. Not all at the same time, but always when I need them. Basic services like DNS/Active Directory are done by the Synology,
which safes resources in the cluster.

![](/images/vcenter2.png)

Software/Solutions I have implemented today:

- vSphere 6.7U3
- vSAN
- NSX-T 2.5
- Enterprise PKS Management Console
- Enterprise PKS
- VMware Integrated Containers
- vRealize Automation 8.0
- vRealize Lifecycle Manager 8
- VMware HCX Enterprise
- vIDM / Workspace ONE
- Nested vSphere Beta

And there are many other things in plan!

---

I am sure, that this will not be the last stage of my homelab and I´m currently planning to buy for another NUC to get my vSAN more reliable and to have more resources in the cluster.


Thanks <a target="_blank" href="http://rguske.github.io">Robert Guske</a> for reviewing!
