# manjaro-update

This Bash script was initially made for myself, so it will make use of Pamac and Meld. Part of the code for the System Maintenance is from ```pacui```

This script will also install Meld to your system in case it's not installed, for the simple reason because it will run a sudo pacdiff command and use Meld for the diff. 

So what is it actually doing?

  - Mirrorsync and system update via Pacman
  - AUR update via Pamac CLI ```pamac update -a``` ( Note that I didn't want to make this a dependency, so it will not install Pamac )
  - Cleaning the System ( Note this will remove all package versions, except the latest 1 )
  - Checks if Meld is installed and runs sudo pacdiff
  - Updates Flatpaks and cleans via ```flatpak uninstall --unused```
  - Updates Snaps
  - Lists all installed Flatpaks and Snaps
  - Shows you how long it did take to run this script in seconds
  - Presents you some nonsense text and a smiley 

