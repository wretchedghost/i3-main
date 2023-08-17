# My i3 Setup
What we have here is my latest i3 config for my workstation. My theme is based on three colors: purple, white, and grey, with hints of orange. 

## Home Screen
Here are some pictures of my screen using scrot. The wallpapers are of one my favorite places in the world: Porto, Portugal. Don't mind the gap on the left screen. That is due to my left screen being a 1920x1080 (16:9) while my right screen is a 1920x1200 (16:10), but it only looks like this in the screenshot not on the hardware itself. 

![my workstation](./Pictures/example/screen.png)

## Rofi
Here is my custom config that make rofi look good, transparent, and highlights the last run program for easy access.

![my workstation](./Pictures/example/rofi_custom.png)

## i3Blocks
I obsfucated my public IP, even though its my tailscale public IP, for obvious reasons.

![my workstation](./Pictures/example/i3blocks.png)

My bar shows icons, workspace number, the weather, when VPNs are connected, private IP address, space left in `/`, RAM, CPU usage and temp, a date that you can click on which opens a dropdown menu calendar, the ability to control the CPU speeds (this is meant for laptops), etc.

## urxvt Terminal
![my_terminal](./Pictures/example/neofetch.png)

I have customized `neofetch` to show the arch logo and the titles in a custom purple color. It took me a good while to find the color I was looking for. You can find it at the bottom of my .bashrc file.

## Theme
![my_theme](./Pictures/example/lxappearance1.png)
![my_theme](./Pictures/example/lxappearance2.png)

## Color Chooser
The site I used to find the colors I was looking for.

[https://htmlcolorcodes.com/colors/](https://htmlcolorcodes.com/colors/)

## Prerequisites and some recomendations
* Arch (This config might work with other distros but I haven't tested it anything other than Arch)
* i3-wm (The new upstream i3 as i3-gaps was merged with i3-wm **FINALLY**!)
* i3blocks (Top Menu Bar)
  * NetworkManager (Needed for nm-vpn Blocket)
  * networkmanager-openvpn
  * perl-json (Needed for weather_NOAA Blocklet)
  * tailscale
* vim (My personal favorite text editor)
* feh (A simple but effective photo viewer and wallpaper setter)
* urxvt-perls (Also my personal favorite terminal emulator once its been configured. Otherwise urxvt is ugly as crap)
* firefox (I swapped from Brave to Firefox due to Chrome and Chrome-clones security/privacy concerns. And especially with Chrome's eventual move to web 3.0)
* rofi (Program/app menu. Replaces dmenu as it is better looking and more configurable) 
* dunst (Notification pop-up program) 
* scrot (For taking screenshots)
* neofetch (Shows hardware and flashy info in the terminal)
* ttf-font-awesome (For all the cool image logos)
* ttf-dejavu (My standard font for everything else)
* ttf-monoid (A great font for the terminal)
* gsimplecal (Simple GUI calendar)
* galculator (Gnome calculator)
* conky (It is designed to show clock and date on main screen in my config)
* picom (Window transperancy and window shadow. A must need for your windows to look extra cool)
* redshift (Sets color screen and can be set on a schedule. Usually only for laptops but can work well on a desktop if you are a night-owl like myself and don't like your eyes to burn with bright white windows)
* thunar or pcmanfm (Both are good file managers. pcmanfm is lighter weight but thunar has some pretty cool options, bulk-rename, etc.)
* voluemicon (Tray volume icon)
* networkmanager-applet (Tray networkmanager icon)

##### AUR
* vimix-icon-theme 
* vimix-gtk-themes 
* vimix-cursors

### For laptops
* acpi
* To allow for laptop lid to enable `i3lock`, create this file and add the below config to `/etc/systemd/system/sleep.target.wants/screenlock.service`:

```text
[Unit]
Description=Starts i3lock at suspend time
Before=sleep.target

[Service]
User=wretchedghost
Type=forking
Environment=DISPLAY=:0
ExecStartPre=
ExecStart=$HOME/.config/i3/scripts/lock_and_blur.sh

[Install]
WantedBy=sleep.target
```

Change `User=` to your username and `ExecStart=` to the location where your i3lock.sh or other config is located.

## Steps to make your setup look like mine
1. Install all of the prerequisite program above.
2. Run `git clone https://github.com/wretchedghost/i3-wretchedbox`.
3. `cd i3-wretchedbox`
4. `cp .* ~/ && cp -R Pictures/Portugal ~/Pictures/`
5. Install `lightdm` and `lightdm-slick-greeter` via package manager. Enable lightdm via systemd by running `sudo systemctl enable lightdm lightdm-slick-greeter`
6. `sudo cp background.jpg /usr/share/pixmaps/`.
7. `sudo cp lightdm/ /etc/lightdm/`. 
8. Run `source ~/.bashrc`.

## What my Lightdm background looks like

![Lightdm](./background.jpg)

## Libreoffice uses a different way to work with a theme so follow below to make it look better

1. cd i3-wretchedbox
2. cp libreoffice-writer.desktop ~/.local/share/applications/

## To-Be-Fixed

* Not really a fix but I am looking at building a script that will install my setup just how I like it. As for right now I have an automated script I built that will install a vanilla arch-linux with no X (GUI) using `ext4`, `LUKS2`, `swapfile`, and a `tmpfs`. 
    * Check it out here: [https://github.com/wretchedghost/easy-arch-ext4](https://github.com/wretchedghost/easy-arch-ext4)
