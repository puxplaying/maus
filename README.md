# maus

This Bash script was made to update and maintain a Manjaro or Arch system with Pacman 
and the alternative package managers - Pamac, Snap and Flatpak in a automatic manner, 
with as little as necessary user intervention required.
It makes use of the functionality of [PacUI](https://github.com/excalibur1234/pacui) 
for the system maintenance.

This script will also install ```meld``` to your system in case it's not installed, for the simple reason because it will run a ```sudo pacdiff``` command and use Meld for the diff, if no ```DIFFPROG``` "Environment Variable" was set by the user, otherwise user settings will be used.

In case you don't want it to check for Meld, comment the function at the end of the script.
```
#_meld
```

So what is it actually doing?

  - Check for database lock file and prompt for removal in case it's present
  - Remove partially downloaded packages
  - Mirrorsync and system update via Pacman
  - AUR update via installed AUR helper: pamac, yay, pikaur, aurman, pakku, trizen, pacaur, paru
  - Search for orphaned packages and prompt for removal
  - Check for failed systemd service(s)
  - Check for broken symlinks
  - Check consistency of local repository
  - Check for packages moved to the AUR
  - Clean systemd log files
  - Clean package cache ( Note this will remove all package versions, except the latest 2 )
  - Check for EOL Kernels
  - Checks if Meld is installed and runs ```sudo pacdiff```
  - (If Installed) Updates Flatpaks and cleans up unused packages
  - (If Installed) Updates Snaps and removes all package versions, except the latest 2
  - Shows you how long it did take to run this script
  
  ---
  
  How to use:
  
   - Make maus executable and run with ```./maus```
   
   If you prefer a menu icon and launcher, install it with:
   
   - ```sudo pacman -Syu base-devel git```
   - ```git clone https://github.com/puxplaying/maus.git```
   - ```cd maus```
   - ```makepkg -srci``` 
   
   After installation:
   
   - click on the *Update* icon in the menu
   
     <img src="https://github.com/puxplaying/maus/blob/master/update.png" alt="update" width="50" height="50" />

   - or run it via ```maus```

---

See ```maus -h``` for advanced options:

```
 Welcome to the Help Page!
 [maus] runs by default without flags, but also provides advanced options.

 maus [option]:

 -a, --aur         - [SET AUR_HELPER]
                     Set the desired AUR Helper manually

 -i, --interactive - [INTERACTIVE MODE]
                     Guided run with more options, includig the (-a, --aur) flag

 -l, --list        - [LIST AUR_HELPER]
                     List all supported AUR Helper

 -h, --help        - This Help Text
```

