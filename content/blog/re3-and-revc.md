+++
title = "RE3 and REVC"
date = 2021-10-28
+++

A while back, I saw a [Reddit post](https://www.reddit.com/r/linux_gaming/comments/lnuwkx/re3_gtarenderware_reverseengineering_project/) from [r/linux_gaming](https://www.reddit.com/r/linux_gaming/) where a reverse engineering project of Grand Theft Auto: III and Vice City was taken down by Take Two for copyright infridgement. Having never heard of the project, I've decided to research about it, and I wished I'd have known about this project sooner.

# What is it?
re3/reVC was a fan made reverse engineering project of the two most popular games, Grand Theft Auto: III and Grand Theft Auto: Vice City that was released back in the early 2000s. This project was meant to optimize both games in a way that it can run on modern and handheld machines (i.e Nintendo Switch), while also applying fixes that would have appeared on the original games. Unfortunately Take Two, the parent company of Rockstar Games, saw this as copyright infridgement, so they sent out a DMCA notice to Github to take down the project. Fortunately, about a month or two later, the developers were able to counter the DMCA and was able to continue hosting and push out more updates until it was taken down again last month.

Even though the updated code has been taken down, I was still interested in the project and run it on my machine. Since the code was on Github, people would download their own copy and re-upload it to other sites. After some reasearching, I was able to grab the latest code files, and compile it. Since I was successful in building the code, I wanted to share my results, gameplay and instructions on compiling the code.

<iframe
    width="560"
    height="315"
    src="https://www.youtube-nocookie.com/embed/HIc_fGfQ-Do"
    title="YouTube video player"
    frameborder="0"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen
>
</iframe>

# How I compiled the code
Note: Instructions can also be found in the video description.
This was built on Arch Linux, using the Zen Kernel (5.14.9)

1. Install the following packages (These are packages for Arch, so you might need to research for the appropriate packages for your desired distro):
    - glew
    - glfw-x11 (or glfw-wayland if you are on Wayland)
    - libsnd
    - mpg123
    - openal
    - cmake
    - premake
    - dos2unix (Might be needed if some of the scripts aren't properly formatted, depending on where you grabbed the source code)
2. Download and extract the source code (Can be grabbed from archive.org, just search for "RE3 and REVC Source Code Backups")
3. Assuming you're already have a terminal open, cd to the re3 directory (ex. /path/to/extracted/code/revc/re3)
4. Add execute permissions to the premake5Linux and printhash.sh script files
5. Run the command: dos2unix printhash.sh (This might not be needed if you have grabbed the source code from somewhere else)
6. Run the command: ./premake5Linux --with-librw gmake2 (if your CPU is ARM/ARM64, you will need to build premake5 first before running this command. You'll need to find instructions on how to do that though)
7. cd to the build directory and run the command: make config=release_linux-amd64-librw_gl3_glfw-oal (or type make help to choose your appropriate config)
8. Once compiled, Copy the all the contents of re3/gamefiles and re3/bin/linux-amd64-librw_gl3_glfw-oal/Release to the game root directory
9. To run the game, cd to the game root directory and type: ./reVC

# My thoughts
Doing this mini project made me continue appreciating the modding community in PC Gaming, whether it be for fixes that companies won't patch, or even the fun texture mods that we're all familiar with, running a 20 year old game on a modern machine wouldn't really exist if mods like these exist.
