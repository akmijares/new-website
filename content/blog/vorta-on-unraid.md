+++
title = "Vorta on Unraid"
date = 2025-04-05
+++

I've been wanting to use Vorta directly on Unraid NAS for a while now for my server backups, as I use it on my main machine to backup to my NAS. I tried the CLI approach with a VM however I couldn't properly configure it, so I gave up on that.

So I retried my search in hopes someone made a Community Apps Template however the one that I found seemed to be Abandonware and that it no longer existed but somehow the support thread was still available.

So my search continues.

Until I found a Github Project that a someone made a [docker version of Vorta](https://github.com/borgbase/vorta-docker).

Perfect, since Unraid has docker support it should be easy to implement to Unraid, I thought.

After some troubleshooting, I was able to deploy the app on my NAS.

It wasn't as hard as I thought.

Deploying is easy, assuming:
1. You know how to use Vorta
2. You've already deployed/edited containers before on Unraid
3. You are backing up to an external server (i.e., borgbase) instead of another locally attached drive

To deploy on Unraid:
1. On the Docker apps, scroll down until you see "Add Container"
2. Toggle Advanced view and enter these values:
- Name: Whatever you want the container name to be
- Repository:
```
ghcr.io/borgbase/vorta-docker:latest
```
- WebUI (Optional but easier to be able to navigate to UI from Unraid):
```
http://[IP]:[PORT:5800]
```
- Extra Parameters:
```
--hostname="[Enter your preferred hostname here, It's recommended from the dev]"
```
![Unraid Values](/img/blog-pics/unraid-vorta/advanced1.jpg)

- Toggle Console shell command to Shell

- Add a new port:
```
1. Container Port: 5800
2. Host Port: 5810 (or another port that you desire)
3. Default value: Same as Host Port
4. Connection Type
```
![Port](/img/blog-pics/unraid-vorta/port.jpg)

- Add a new path (This is where the config files will be located):
```
1. Name: Config
2. Container Path: /config (You can also change this if you wish)
3. Host Path: /mnt/user/appdata/vorta 
4. Default value: Same as Host Path
5. Access Mode: Read/Write
```
![Config Path](/img/blog-pics/unraid-vorta/config-path.jpg)

- Add another path (This is the directory that you want to backup):
```
1. Name: Data
2. Container Path: /data (Can be changed if you wish)
3. Host Path /mnt/user (You can be specific and point to your desired directory/share within /mnt/user if you choose)
4. Access Mode: Read Only
```
![Data Path](/img/blog-pics/unraid-vorta/data.jpg)

- Add a variable (This sets your timezone, especially if you want to schedule backups)
```
1. Name: Timezone
2. Key: tz
3. Value: [Insert your timezone here]
```
![Timezone](/img/blog-pics/unraid-vorta/tz.jpg)
3. Build the docker container. If successful, you should be able to navigate to the url: https://[ServerIPgoeshere]:5810

Now once the Vorta WebUI loads, you will need to generate its SSH key in order for the server to recognize it. If you use the default settings to generate the key, it'll save at:
```
/mnt/user/appdata/vorta/.ssh
```
Or you if you launch the docker shell, you can view it at:
```
/config/.ssh
```

It'll also copy the public key to the VNC clipboard once you generate, which appears on the left side of the screen.

I won't discuss if you want to mount the archives within the docker container, I'm not going through that approach, and it's probably better if you want to restore it would be on a different machine anyway. However if you want to go through that steps, you can read the docs from [Github](https://github.com/borgbase/vorta-docker)

I'll probably create a community app template on Unraid at some point, once my backups are stable (also if I get the developers' permission).
