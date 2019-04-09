# horizontal-grub
This script will transform the current grub configuration file generated by grub(2), to a fake-horizontal style.

This bash script was created with focus on multi-booting systems and combined with [horizontal-grub](https://github.com/petsam/prettygrub) Grub theme.
There is no reason to use it if you are not multi-booting, either with other Linux installations, or with non-linux systems supported by Grub.
It is developed and tested on Manjaro Linux (Arch based), but it should also work on other Linux systems, perhaps with minor modification. I would appreciate any reports from users of any other distributions, or with mixed multi-booting systems, either verifying it works on their system, or reporting bugs and providing info (the files in the temporary working directory), so I try to fix any conflicts, or bugs.

### Requirements
* Multi-booting system
* Enabled os-prober in /etc/default/grub
* bash, awk
* polkit/pkexec (optional, for saving the new configuration to system)


### Installation (suggested):
```
git clone https://github.com/petsam/horizontal-grub.git
chmod +x horizontal-grub
sudo cp horizontal-grub /usr/local/bin/
```

### Usage
* Install a PrettyGrub compatible grub theme
* Verify you have this in /etc/default/grub
```
GRUB_DISABLE_OS_PROBER=false
```
* Update grub configuration (with `update-grub` or grub-mkconfig)
* Run in terminal (as a normal user)
```
horizontal-grub
```
or using a custom `grub.cfg` file (generated by grub)
```
horizontal-grub [PATH-TO-FILE]
```
After a successful creation, you will be asked to save to system, or locally.
If you choose to copy to system, a backup of your current grub.cfg will be created.
If you choose to save locally, to review before saving to system, a suggested copy command will be printed in the output.