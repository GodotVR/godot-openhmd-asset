# Godot OpenHMD GDNative module
This module is provided as is, all files are contained within the addons/godot-openhmd folder

At this point in time this asset only has a Windows 64bit build. Mac OS X and Linux builds will follow soon.

Source code for this module can be found here:
https://github.com/GodotVR/godot_openhmd

Also note that we have a support asset containing a number of useful scenes to get you going building VR applications in Godot:
https://github.com/GodotVR/godot-vr-common

Setting up OpenHMD
------------------
The OpenHMD solution currently does not support rendering directly to the HMD. Output for both eyes will be to the main Godot window. You will need to configure your Godot project to run fullscreen and mirror the display.

A version that handles direct output to the HMD in a similar fashion as the OpenVR and Oculus modules do will hopefully become available in the not too distant future.

Because OpenHMD supports multiple devices there is a configuration object you need to instantiate first:
```
# get our configuration object
openhmd_config = preload("res://addons/godot-openhmd/OpenHMDConfig.gdns").new()
```

After instantiating this object you will need to set up the ARVR interface:
```
var interface = ARVRServer.find_interface("OpenHMD")
if interface and interface.initialize():
	get_viewport().arvr = true
```

By default the first active HMD that is found will be automatically used.

Further documentation will follow soon.

Licensing
---------
The Godot OpenHMD module is supplied under an MIT License. The LICENSE file in this repository only covers the Godot part of the module.
OpenHMD itself falls under a BSL-1.0 license.
This module further uses:
- hidapi which is released under various licenses, see http://www.signal11.us/oss/hidapi/ for more details
- libusb which is released under a LGPL-2.1 license

About this repository
---------------------
This repository was created by and is maintained by Bastiaan Olij a.k.a. Mux213

You can follow me on twitter for regular updates here:
https://twitter.com/mux213

Videos about my work with Godot including tutorials on working with VR in Godot can by found on my youtube page:
https://www.youtube.com/channel/UCrbLJYzJjDf2p-vJC011lYw
