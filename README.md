# manjaro-update

This Bash script was made to update and maintain a Manjaro system with Pacman 
and the alternative package managers - Pamac, Snap and Flatpak in a automatic manner, 
with as little as necessary user intervention required.
It makes use of the functionality of PacUI 
for the system maintenance. https://github.com/excalibur1234/pacui

This script will also install Meld to your system in case it's not installed, for the simple reason because it will run a ```sudo pacdiff``` command and use Meld for the diff if no Environment Variable was set by the user, otherwise user settings will be used.

In case you don't want it to check for Meld, comment the function at line 434.
```
#_install "${package}";
```

So what is it actually doing?

  - Check for database lock file and remove it in case it's present
  - Remove partially downloaded packages
  - Mirrorsync and system update via Pacman
  - AUR update via Pamac CLI [```pamac update -a```] 
  ( Note that I didn't want to make this a dependency, so it will not install Pamac )
  - Search for orphaned packages and prompt for removal
  - Check for failed systemd service(s)
  - Check for broken symlinks
  - Check consistency of local repository
  - Check for packages moved to the AUR
  - Clean systemd log files
  - Clean package cache ( Note this will remove all package versions, except the latest 2 )
  - Check for EOL Kernels
  - Checks if Meld is installed and runs ```sudo pacdiff```
  - (If Installed) Updates Flatpaks and cleans via ```flatpak uninstall --unused --delete-data```
  - (If Installed) Updates Snaps
  - (If Installed) Lists all installed Flatpaks and Snaps
  - Shows you how long it did take to run this script in seconds
