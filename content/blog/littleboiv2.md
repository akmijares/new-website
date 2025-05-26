+++
title = "Littleboi V2"
date = 2025-05-26
+++

So with my main NAS that I've had a for a while now, about a year ago I built a secondary server which it's main purpose to be another backup for the important files that I wouldn't want to lose, aka the [3-2-1 backup strategy](https://www.backblaze.com/blog/the-3-2-1-backup-strategy/).

Although, the problem is, that this backup server was this decade old Netgear NAS that I got for free from work, which is by the way, [discontinued](https://www.netgear.com/support/product/rn316/).

What were the issues if you wondering?
1. Slow backups (even with the added ram stick)
2. It would sometimes freeze whenever I was looking through something the Unraid UI

So, I did some digging, and I wanted to build something, as anything really would be 1000x better than that.

Sure I could've gone with a similar approach and just buy a Synology/QNAP, however:
1. I've already loaded up Unraid on a USB and already configured everything, so I don't really want to lose the license,
2. Synology announced that their NAS will only work on their ["approved" drives](https://www.theverge.com/news/652364/synology-nas-third-party-hard-drive-restrictions), and I don't know if QNAP will take that approach as well.


My goal was to spend less than 700, which meant going on the used market, which was fine with me as this will just be a destination backup server.

Here's what I stumbled upon:
1. [3700x](https://www.techpowerup.com/cpu-specs/ryzen-7-3700x.c2130) + [Hyper 212 cooler](https://www.coolermaster.com/en-global/products/hyper-212-evo/) (cooler wasn't part of the plan, but it was bundled for an extra $5) = $95 (used)
2. [Node 804](https://www.fractal-design.com/products/cases/node/node-804/black/) + [Kingston 32GB ECC](https://www.kingston.com/en/memory/search?partid=KSM32ED8/16HD) (The Ram being ECC was a bonus) = $160 (used)
3. [Asrock Pro Motherboard](https://www.asrock.com/mb/AMD/B550M%20Pro4/index.asp) = $130
4. [Corsar RME 650W](https://www.corsair.com/ww/en/p/psu/cp-9020233-ww/rm-series-rm650-650-watt-80-plus-gold-fully-modular-atx-psu-ww-cp-9020233-ww) = $131
5. [LSI Card for the Drives](https://www.ebay.ca/itm/163563898712) = $100 (used)

The only thing I bought for new was the Motherboard and the PSU, everything else was used.

The result? A server that is 10000x better than what I had before.

So much better in fact that I've decided setup a 3rd pihole so that my network will at least have 2 DNS servers to query if one ever goes down.

Since I now have a powerful secondary backup server, I'll most likely expand my homelab even further, add several more docker containers, who knows. 

The network is my oyster.
