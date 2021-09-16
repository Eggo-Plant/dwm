# My DWM configs
> There are a couple dependencies that are used in the keybinds, the config will work without them, but it'll lack some functionality.

# Dependencies
* `slock` - Simple X display locker
* `maim` - Screenshot tool
* `xclip` - Provides functionality for maim to copy to clipboard
* `ncmpcpp` - NCurses interface to control mpd
* `mpc` - Allows keybinds to control mpd
* `chromium` - Allows for opening of discord in sandboxed "app" mode

**Arch Linux Dependency Installation**
```
# pacman -S slock maim xclip ncmpcpp mpc chromium
```

**Other Distros**
idk figure it out

# Installation
Clone the repo
```
$ git clone https://github.com/Eggo-Plant/dwm && cd dwm
```
Compile and install dwm
```
# make clean install
```

Now add `exec dwm` to your `~/.xinitrc` file.

# Tips
If you want the time to show up in the top right if your screen you can put this block of shell code inside of your `/.xinitrc` file before `exec dwm`
```sh
export first=0
while true; do
   xsetroot -name " $(date +"%b %d | %I:%M%P" )"
   if [ $first -eq 0 ] ; then
      ((offset=60 - $(date +"%S")))
      sleep $offset
   else
      sleep 1m
   fi
   export first=1
done &
```
