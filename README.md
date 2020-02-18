# Getting Started With Arch
## 02/10/2020: Starting on my own  
I tried installing Arch from scratch on my laptop which used to run Windows 10. As the newcomer I am, this came with a lot of problems.  
### Using the installation guide provided by Arch's wiki
I used [the wiki guide](https://wiki.archlinux.org/index.php/installation_guide) to install Arch on my laptop. I wanted to work as quickly as possible and by doing that I didn't read the whole file, which ended badly. I actually ended up deleting my UEFI which only gave me more problems. Thus I ended up asking a [friend](https://github.com/angelocarly) for help, who has been using Arch for a while.  

## 02/11/2020: That's what friends are for  
We met up at school were my friend gave me some quick tips on how to install Arch, so we sat side by side and started installing it. Since I deleted my UEFI we had to configure a new one which actually worked first try. After the clean installation of Arch we kept getting this "no bootable device found" instead of the Grub screen. We found out that Acer laptop that I'm using has [this common bug](https://itsfoss.com/no-bootable-device-found-ubuntu/) where it messes with the UEFI boot settings. Thus the "Secure Boot Mode" had to be set back to "On" after installing through USB for which it had to be set to "Off".
We got it to start up and called it for today.  

## 02/12/2020: Driven to make it work
I started by applying the basic configuration for my new system.  
* Added my passwd for root
* Added a basic user with a pass
* Put myself into multiple groups (wheel,audio,video,optical,storage)  

After this I started setting up my wired network connection. I actually struggled again because Arch sets DHCPCD on inactive out of the box which I didn't notice at first. After finding out I got it to work. I could ping archlinux.com but now I wanted to setup the wireless connection so I can use my laptop wherever I want. Using the 
*ip link set interface up* command didn't actually up my interface. Because when you use "Netctl" you need to put the interface in a downed state first or it won't configure otherwise. After this I started my profile which is automatically configured by using the *wifi-menu* command and got it to work aswell. Hooray!  

I had to uncomment *%wheel ALL=(ALL) ALL* in the sudoers file to make sure I can use sudo commands. I also had to change my keymap in "/etc/vonconsole.conf", into *KEYMAP=be-latin1*, this does give a warning-message but it works.

## 02/14/2020: My love for Arch is starting to grow 
And no, this is not because it's valentines day, or is it?
I actually thought about Arch alot during the past days: "What should I install?", "What can I do besides just having an OS?", "What will I learn during the process",...  
I start my day watching a [video](https://www.youtube.com/watch?v=-dEuXTMzRKs) about Pacman of which I made my [PacmanCheatSheet](CheatSheets/PacmanCheatSheet.md)  
After this I've set up github so I can write on my laptop instead of using my desktop.

## 02/15/2020: More packages
Today I wanted to install more packages and maybe start installing a desktop environment. For my packages I installed the following:  

* base-devel
* dosfstools 
* os-prober
* mtools
* linux-headers
* linux-lts
* linux-lts-headers
* network-manager-applet 
* networkmanager 
* wireless_tools 
* wpa_supplicant 
* dialog 
 
I actually got some errors with "base-devel", "os-prober" and "network-manager-applet", I will try to fix these later. 

## 02/18/2020: It's been a while  
A fix has been found for the error when installing the packages, since we did an offline install, we forgot to run *pacman-key --init* and *pacman-key --populate archlinux*
I'm back and driven to get this desktop environment working, I start off by installing "xorg-server", which is used to draw the graphical interface.  
For this I also need to install the video driver, my system is running a **Intel Corporation HD Graphics 620** and a **NVIDIA GEFORCE 940MX**. 
If you don't know which card you have, run the "lspci" command. To know which package to install, just do a quick google search and you'll find it.  
I install **bspwm** on recommendation, using the [Arch bpswm wiki](https://wiki.archlinux.org/index.php/Bspwm).   
After the initial configuration I install a "terminal emulator", which I edit in "~/.config/sxhkd/sxhkdrc". 

