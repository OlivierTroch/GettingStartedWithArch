# GettingStartedWithArch
## 02/10/2020: Starting on my own  
I tried installing Arch from scratch on my laptop which used to run Windows 10. As the newcomer I am, this came with a lot of problems.  
### Using the installation guide provided by Arch's wiki
I used [the wiki guide](https://wiki.archlinux.org/index.php/installation_guide) to install Arch on my laptop. I wanted to work as quickly as possible and by doing that I didn't read the whole file, which ended badly. I actually ended up deleting my UEFI which only gave me more problems. Thus I ended up asking a [friend](https://github.com/angelocarly) for help, who has been using Arch for a while.  

## 02/11/2020: That's what friends are for  
We met up at school were my friend gave me some quick tips on how to install Arch, so we sat side by side and started installing it. Since I deleted my UEFI we had to configure a new one which actually worked first try, thank god. But still we kept getting this "No bootable device found" error. This left us thunderstruck because we followed every single step. After the clean installation of Arch we kept getting this "no bootable device found" instead of the Grub screen. We found out that Acer laptop that I'm using has [this common bug](https://itsfoss.com/no-bootable-device-found-ubuntu/) where it messes with the UEFI boot settings. Thus the "Secure Boot Mode" had to be set back to "On" after installing through USB for which it had to be set to "Off".
We got it to start up and called it for today.  

## 02/12/2020: Driven to make it work
I started by applying the basic configuration for my new system.  
* Added my passwd for root
* Added a basic user with a pass
* Put myself into multiple groups (wheel,audio,video,optical,storage)  

After this I started setting up my wired network connection. I actually struggled again because Arch sets DHCPCD on inactive out of the box which I didn't notice at first. After finding out I got it to work. I could ping archlinux.com but now I wanted to setup the wireless connection so I can use my laptop wherever I want. Using the 
*ip link set interface up* command didn't actually up my interface. Because when you use "Netctl" you need to put the interface in a downed state first or it won't configure otherwise. After this I started my profile which is automatically configured by using the *wifi-menu* command and got it to work aswell. Hooray!  

I had to uncomment *%wheel ALL=(ALL) ALL* in the sudoers file to make sure I can use sudo commands. I also had to change my keymap in "/etc/vonconsole.conf", into *KEYMAP=be-latin1*, this does give a warning-message but it works.
