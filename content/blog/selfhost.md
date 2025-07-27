+++
title = "Host all the things!"
date = 2025-07-27
+++


So I've been recently exploring ways to expand my homelab even further, figuring out ways to self host more stuff/optimizing my homelab.

My current HomeLab setup:
1. BigBoi, which is the main powerhouse. Runs Plex, hosts VMs, grabs Linux ISOs, etc.
2. LittleBoi, which is a secondary backup for my network.
3. optiplex-proxmox, a used optiplex that runs Linux containers (LXC) on Proxmox. Turns out I should use Proxmox more often.

Here's what I've done so far over the course of half a year:
1. Gradually moving from [ZeroTier](https://www.zerotier.com/) to [Tailscale](https://tailscale.com/). Mainly since due to the increased device count and the granular access controls for my friends.
2. Automating the ability to grab Linux ISOs with the arr stack. If you know, you know. :)
3. NextCloud hosting. I've always wanted to have some sort of "drop", where if I fail to share file due to its size limitations I could just share it through here. I've tried it before through VPS, however I didn't really want to pay $ every month just for nextcloud. 

And then, this past weekend I found an app called [Uptime Kuma](https://github.com/louislam/uptime-kuma), which allows you to self host a monitoring tool for everything in your network. One of things I found was that you can have status pages display the devices that you were monitoring. 

So an idea came, why don't I try and see if I can create a status page, where it monitors Plex & my main server where I can share it to my friends/peers so they can see if it's down.

So after some trial and error, I've done it. I've even tied it under one of my domains, which you can view if you wish: [status.sp33dyboi.xyz](https://status.sp33dyboi.xyz)

I even created a status page for anything [akmijares.ca](https://status.akmijares.ca) related.

I wonder what's next in my homelabbing adventure?
