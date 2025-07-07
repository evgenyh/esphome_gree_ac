# Open source WIFI module replacement for Gree protocol based AC's for Home Assistant.
This repository adds support for ESP-based WiFi modules to interface with Gree/Sinclair AC units.
It's forked from https://github.com/piotrva/esphome_gree_ac, big thanks to @piotrva for his work!

My fork currently differs from the original code in the following ways:

1) I fixed the fan mode, tested on Gree/Daizuki/TGM AC's.
2) I fixed the dropping of commands
3) I fixed the rejection of commands
4) I implemented an optional silent mode (no beeping), only works for module sent commands (not for
   remote control sent commands)
   
It's now compatible with GRJWB04-J / Cs532ae wifi modules

# Current state:
No known problems! if you run into an issue though, please let me know.

# HOW TO 
You can flash this to an ESP module. I used an ESP01-M module, like this one:
https://nl.aliexpress.com/item/1005008528226032.html
So that’s both an ESP01 and the ‘adaptor’ board for 3.3V ↔ 5V conversion (since the ESP01 uses 3.3V and the AC uses 5V).


Create a new project in the ESPbuilder from Home assistant and use my YAML (from the examples directory), copy or modify the info from the generated YAML to mine, where it says '[insert yours]'.
Then you should be able to compile it. I think you can flash directly from Home Assistant,
but I downloaded the compiled binary and flashed with: https://github.com/esphome/esphome-flasher/releases

See the 2 photos for wiring (for flashing and the wiring for connecting it to your AC).

After you've connected the module to your AC, it should pop under settings/integrations/esphome as a 'new device'. If not, check if it started a WIFI access point, which it will do if it can't connect to your home wifi. You can then configure it from there (via 192.168.4.1)

**USE AT YOUR OWN RISK!**
