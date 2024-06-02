# XORG-Config-for-Ultrawide
This is an old configuration file I created under XORG for my 32:9 monitor under Arch Linux.
Since I created my new AMD PC to run Arch Linux under Wayland, I do not need this anymore. But, I figured someone else can put it to use.

## How To Install
You will need to create a `xorg.conf` in the directory `/etc/X11`. You can do this by "touching" in the directory by using this command: `touch xorg.conf`.
The configuration is pasted below. Depending on specifics of the monitor, `xrandr` command can give the exact resolution and Hz to input. 

```c
Section "ServerLayout"
    Identifier     "Layout0"
    Screen      0  "Screen0" 0 0
    InputDevice    "Keyboard0" "CoreKeyboard"
    InputDevice    "Mouse0" "CorePointer"
    Option         "Xinerama" "0"
EndSection

Section "Files"
EndSection

Section "Module"
    Load           "dbe"
    Load           "extmod"
    Load           "type1"
    Load           "freetype"
    Load           "glx"
EndSection

Section "InputDevice"
    # generated from default
    Identifier     "Mouse0"
    Driver         "mouse"
    Option         "Protocol" "auto"
    Option         "Device" "/dev/psaux"
    Option         "Emulate3Buttons" "no"
    Option         "ZAxisMapping" "4 5"
EndSection

Section "InputDevice"
    # generated from default
    Identifier     "Keyboard0"
    Driver         "kbd"
EndSection

Section "Monitor"
    # HorizSync source: edid, VertRefresh source: edid
    Identifier     "Monitor0"
    VendorName     "Unknown"
    ModelName      "Samsung LC49G95T"
    HorizSync       357.0 - 357.0
    VertRefresh     60.0 - 240.0
    Option         "DPMS"
    Option          "PreferredMode" "5120x1440"
EndSection

Section "Device"
    Identifier     "Device0"
    Driver         "nvidia"
    VendorName     "NVIDIA Corporation"
    BoardName      "NVIDIA GeForce RTX 3070 Ti"
EndSection

Section "Screen"
    Identifier     "Screen0"
    Device         "Device0"
    Monitor        "Monitor0"
    DefaultDepth    24
    Option         "Stereo" "0"
    Option         "nvidiaXineramaInfoOrder" "DFP-3"
    Option         "metamodes" "5120x1440_240 +0+0"
    Option         "SLI" "Off"
    Option         "MultiGPU" "Off"
    Option         "BaseMosaic" "off"
    SubSection     "Display"
        Depth       24
    EndSubSection
EndSection</code></pre>
```

-----
As a note, you could always use the `nvidia-settings` application if you have an Nvidia card. Though, I should warn you, it is not well kept.
