# Cheat sheet for package manager **Packman**

## Basic commands

| Task                                       | Command                                                |
| :---                                       | :---                                                   |
| Pacman -S                                  | Installing package                                     |
| Pacman -R                                  | Removing package (use extra options)                   |
| Pacman -Rs                                 | Removes package and dependencies                       |
| Pacman -Rns                                | Removes package, dependencies and system files         |
| Pacman -Sy                                 | Synchronize packages                                   |
| Pacman -Syy                                | Synchronize packages again (double check)              |
| Pacman -Su                                 | update package that have been synchronized             |
| Pacman -Syu                                | Synchronize and update package                         |
| Pacman -S                                  | Installing/updating                                    |
| Pacman -Sw                                 | Downloads package without installing                   |
| Pacman -Sc                                 | Clear out all of the old installations                 |

## Advanced commands  

| Task                                       | Command                                                |
| :---                                       | :---                                                   |
| Pacman -Ss                                 | Search and print a package                             |
| Pacman -Q                                  | Lists every single package                             |
| Pacman -Qe                                 | Lists every single package you installed               |
| Pacman -Qeq                                | Only provides the core, no details                     |
| Pacman -Qn                                 | Lists every single package from main repo's            |
| Pacman -Qm                                 | Lists every single package from the AUR<sup>1</sup>    |
| Pacman -Qdt                                | Lists every single dependency that is uneeded          |

## Changing /etc/pacman.conf
Here I will change settings for the output of pacman.
* Uncomment "Color" under "Misc options" to change the color of the font
* Uncomment "CheckSpace" under "Misc options", the output will let you know if there's enough disk space
* add "ILoveCandy" under "Misc options" for an easter egg

## Changing the mirrorlist in /etc/pacman.d/mirrorlist
delete all the mirrors who are not close by.<sup>2</sup> After around 20 entries, delete the rest.

## Extras
<sub>1 =  Arch User Repository</sub>  
<sub>2 =  Keep the neighboring countries</sub>
