# How use custom touchpad gesture on touchpad
I am using ArchLinux.
You should download libinput-gestures, xdotool, libinput-gestures-install.

```libinput-gestures-setup start```(To make gestures work at startup: use ```autostart```)

```libinput-gestures -l``` -- you will see that you do not have a touchpad connected.

You must add input to your user's group
```
sudo groupadd -f input
sudo gpasswd -a <user> input
```
And you next commands: ```groups <user>```

On next step you must logout and login into your account.
Start gesture setup: ```libinput-gestures-setup start```
```libinput-gestures -l``` 
You should see the input device found, this is your touchpad.
And Final step you should open config file gestures:
```code ~/.config/libinput-gestures.conf```
And add your shortcuts. For example: 
```
gesture swipe left 3 xdotool key ctrl+F1
gesture pinch out 3 xdotool key ctrl+F3
```
Save file and restart libinput-gestures:
```libinput-gestures-setup restart```


Finish. 
Good luck.



