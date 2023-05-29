

# === Manage peripheral ===

## == xinput ==

xinput allow to change peripheral settings

The basics command to set a setting is like so:
> `xinput set-prop <device-id> <property-id> <value>`

Get the list of id with:
> `xinput list`

Get the list of settings for a device with:
>`xinput list-props <device-id>`
>Take note the setting number that is in bracket.

` ` The device id listed in xinput is not permanent and can change when rebooting.  
For scripting, use the name of the device instead.


## == Manage mouse settings ==

Change the settings of the mouse with `xinput`

Example: 

- Sensibility: `xinput set-prop <mouse-id> <accel speed prop id> -0.5`
- Remove mouse acceleration: `xinput set-prop <mouse-id> <libinput accel profile enabled id> 0, 1` 


## == Manage screen settings ==

Use `xrandr` to list the monitors with the resolution and refresh rate available.  
The current refresh rate is marked with an asterisk.

Change the refresh rate to 144hrz with:
> `xrandr -r 144`
