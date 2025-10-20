# Raspbererry-Pi-OS-trixie-on-PC-or-laptop
Installing modern Raspbererry Pi OS trixie on x64 PC or laptop.

# Installing debian Trixie
1. Download the Debian Trixie net installer ISO from [here.](https://www.debian.org/)
2. Flash the ISO onto a USB drive.
3. Boot into the USB drive and go through the installation proccess to install Debian Trixie onto your computer.
(It is recommended to not setup a seperate root user or install any desktop environment to have the most Raspberry Pi OS experience)
# Installing Raspberry Pi OS Trixie repositories.
1. After booting into Debian Trixie, navigate to the `/etc/apt/sources.list.d/` directory by typing the following command `cd etc/apt/sources.list.d/`
2. In the `etc/apt/sources.list.d` directory create a text file called `raspios.list` by typing the following command `sudo touch raspios.list`
3. Add the following line of text "`deb [trusted=yes] http://archive.raspberrypi.org/debian/ trixie main`" into the text file typing the following command `sudo echo "deb [trusted=yes] http://archive.raspberrypi.org/debian/ trixie main" > raspios.list`
4. when the previous step has been completed update your computers repositories by typing `sudo apt update` (this will give you a message about ignoring some repositories and that some repositories don't have a GPG key, but ignore those errors), and if some packages need to be upgraded then type `sudo apt upgrade`.
5. reboot your computer by typing `sudo reboot`
# Installing modern Raspberry Pi Wayland desktop.
1. To install the Raspberry Pi Wayland desktop type `sudo apt install rpd-wayland-all`
2. Reboot your computer by typing `sudo reboot` and you should enter straight into the Raspberry Pi desktop login screen.
# Installing modern Raspberry Pi X11 Desktop.
1. To install the Raspberry Pi X11 desktop type `sudo apt install rpd-x-all`
2. Reboot your computer by typing `sudo reboot` and you should enter straight into the Raspberry Pi desktop login screen.
# Enabling The Raspberry Pi splashscreen on boot.
1. To enable the Raspberry Pi splashscreen on boot you must first go to the default Raspberry Pi configuration script by typing the following command `sudo raspi-config`
2. Once you are in the Raspberry Pi configuration menu navigate with your arrow keys to System Options>Splash Screen>
3. It will then ask you if you'd like to enable the splash at boot, click "yes" and then "Ok".
4. Now you should be back in the main menu, click the TAB key and then the RIGHT ARROW key and then the ENTER key to exit the Raspberry Pi configuration script.
5. If it has not already asked you to reboot then type `sudo reboot`.
6. Congradulations! You now have the full Raspberry Pi Trixie OS desktop experience!
# Unresolved issues.
You cannot choose which Wi-Fi network you want directly from the Raspberry Pi Desktop GUI. You must either use the Raspberry Pi configuration script or use the`networkctl` command from the termimal.
(To use the `networkctl` command you must first enable the networkctl daemon by typing `sudo systemctl enable systemd-networkd.service` and then rebooting your computer.)
