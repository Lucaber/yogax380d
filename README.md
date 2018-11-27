# Automatic tablet mode on Thinkpad X380 Yoga

This is a fork of [yoga370d](https://github.com/hensur/yoga370d) for the new Thinkpad X380 Yoga and i3-wm. 
The Thinkpad X380 Yoga is a convertible laptop, so you can flip the screen over and your laptop is now a tablet.
I had to install [iio-sensor-proxy](https://github.com/hadess/iio-sensor-proxy) to have working screen rotation.

However, this leaves the touchpad and trackpoint enabled. This tool will detect if the Yoga is in Tablet mode and disable these devices.
It will also disable the Wacom Finger Touch if the pen is near the screen.

I've tested it on ArchLinux with kernel 4.14.13-1-ARCH. It should work on other distros as well.

## prerequisites
* linux packages: `xorg-xrandr acpid python-dbus iio-sensor-proxy python-docopt xorg-xinput xf86-input-wacom python`

## usage

This python script provides the following features:

* Listen to dbus signals from sensor proxy and detect when the laptop is converted to tablet mode. Then touchpad and trackpoint are switched off. When going back to laptop mode the orginal state is restored.
* disable finger touch if stylus is close to the display
* upon termination, switch on touchpad and trackpoint
* screen rotation with i3 restart

```
./yogax380d
```

## References/Kudos

* https://github.com/hensur/yoga370d
* https://github.com/sarmbruster/thinkpad_x1_yoga_rotation
* https://classicforum.manjaro.org/index.php?topic=9671.0
* https://github.com/wdbm/spin 
