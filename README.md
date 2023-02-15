# My i3 Setup

What we have here is my latest i3 config for my workstation. 

#### Pics

Here are some pictures of my screen using scrot. The wallpapers are of one my favorite places in the world, Portugal.

![my workstation](./Pictures/example/screen.png)

#### Rofi

![my workstation](./Pictures/example/rofi_custom.png)

#### i3Blocks

![my workstation](./Pictures/example/i3blocks.png)

#### urxvt Terminal

![my_terminal](./Pictures/example/neofetch.png)

#### Color Chooser
[https://htmlcolorcodes.com/colors/](https://htmlcolorcodes.com/colors/)

#### Prerequirements and recomendations

* Arch (but might work with other distros)
* i3-wm (The new upstream i3 as i3-gaps was merged with i3-wm **FINALLY**!)
* i3blocks (Top Menu Bar)
  * NetworkManager (Needed for nm-vpn Blocket)
  * networkmanager-openvpn
  * perl-json (Needed for weather_NOAA Blocklet)
  * tailscale
* vim (My personal favorite editor)
* feh (A simple but effective photo viewer and wallpaper setter)
* urxvt-perls (Also my personal favorite terminal emulator once its been configured. Otherwise urxvt is ugly as crap)
* firefox (I swapped from Brave to Firefox due to Chrome and Chrome-clones security/privacy concerns. And especially with Chromes eventual move to web 3.0)
* rofi (Program/app menu. Replaces dmenu) 
* dunst (Notification pop-up program) 
* scrot (For taking screenshots)
* neofetch (Shows hardware and other important info in the terminal)
* ttf-font-awesome (For all the cool image logos)
* ttf-dejavu (My standard font for everything else)
* ttf-monoid (A great font for the terminal)
* gsimplecal (Simple GUI calendar)
* galculator (Gnome calculator)
* conky (Used to show clock on main screen)
* picom (Window transperancy and window shadow)
* redshift (Sets color screen and can be set on a schedule. Usually only for laptops but can work well on a desktop if you are a night-owl like myself)
* thunar or pcmanfm (Both are good file managers)
* voluemicon (Tray volume icon)
* networkmanager-applet (Tray networkmanager icon)

#### Laptop

* acpi (Only needed if you have a laptop)

#### Step to make your setup to look like mine

1. install lightdm lightdm-slick-greeter
2. place background.jpg in /usr/share/pixmaps/
3. copy lightdm/ into /etc/lightdm/

![/images/lightdm.png](/images/lightdm.png)

> Optional
1. copy-in-place libreoffice-writer.desk into ~/.local/share/applications/libreoffice-writer.desktop

##### To-Be-Fixed

1. gsimplecal has a weird bug where it will stay popped-up even when you click off of it. Getting rid of it is as simple as hitting $mod+Shift+q when hovered over gsimplecal.
