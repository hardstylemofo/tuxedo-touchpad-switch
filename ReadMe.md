# About
This a Linux userspace driver to enable and disable the touchpads on TongFang/Uniwill laptops using a HID command. **This will trigger the touchpad-disabled-LED, formerly unfunctional under linux.**

Most desktop environments already have a way to disable the touchpad, but this setting never reaches the firmware of the device. This driver listens to the session D-Bus and dispatches the approprita HID call to /dev/hidraw* whenever the setting changes, closing the gap to the device itself, and enabling the built in LED.

Currently this driver was only tested and works on the GDM greeter, GNOME Shell, Budgie, and KDE Plasmashell. All other environments, including the tty-console, work as before, meaning touchpad is always enabled on the HID level.

Author: Werner Sembach <tux@tuxedocomputers.com>

# Building

## Testing
```
$ sudo apt install libudev-dev libglib2.0-dev
$ mkdir build
$ cd build
$ cmake ..
$ sudo make install
$ sudo reboot
```
```
A prebuilt .deb package is already created under the Releases section.
# Installing
Grab the latest .deb package and install it like this:
  sudo dpkg -i tuxedo-touchpad-switch_1.0.4_amd64.deb
  
  After installing, reboot your PC.
