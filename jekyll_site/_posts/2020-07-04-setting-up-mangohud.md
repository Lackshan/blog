---
layout: post
title: "Setting Up MangoHud"
date: 2020-07-06 00:18:00
categories: 
---
During my time benchmarking and [undervolting my RX 480]({% post_url 2020-07-04-undervolting-rx480 %}), I stumbled upon [MangoHud](https://github.com/flightlessmango/MangoHud). This post will detail how I installed, configured and enabled it:

Installation will vary by distro but since I'm using Fedora 31, I ran:
```bash
sudo dnf install mangohud
```


Once that's done, we will need to create a config file. I opted for a global config but you can choose to make a per application config instead. Firstly, we will create the directory ```~/.config/MangoHud``` by running:
```bash
mkdir ~/.config/MangoHud
```
Then to create and edit the config, we run:
```bash
nano ~/.config/MangoHud/MangoHud.conf
```


An example config is available in the [MangoHud repo](https://github.com/flightlessmango/MangoHud/blob/master/bin/MangoHud.conf). Here's my edited config:
```
################ PERFORMANCE #################

### Limit the application FPS
# fps_limit=

### VSYNC [0-3] 0 = adaptive; 1 = off; 2 = mailbox; 3 = on
vsync=1

### OpenGL VSYNC [0-N] 0 = off; >=1 = wait for N v-blanks, N > 1 acts as a fps limiter (fps = display refresh rate / N)
gl_vsync=0

################### VISUAL ###################
cpu_stats
cpu_temp
cpu_text = CPU

ram

gpu_stats
gpu_temp
gpu_core_clock
gpu_mem_clock
gpu_power
gpu_text = GPU

vram

vulkan_driver

### Display loaded MangoHud architecture
# arch

### Display the frametime line graph
frame_timing
histogram

font_size=24
# font_scale_media_player = 0.55

position=top-left
background_alpha=0.5

### Color customization
text_color=FFFFFF
gpu_color=2E9762
cpu_color=2E97CB
vram_color=AD64C1
ram_color=C26693
engine_color=EB5B5B
io_color=A491D3
frametime_color=00FF00
background_color=020202
media_player_color=FFFFFF

################## INTERACTION #################
toggle_hud=Shift_R+F12
toggle_logging=Shift_L+F2
reload_cfg=Shift_L+F4

################## LOG #################
output_file=/home/lackshan/Documents/MangoHudLogs/MangoHudLogfile
```
Copy and paste it into your config file and save it (if you're using ```nano``` press ```Ctrl + X``` and then press ```Y``` to save and exit).

Now all that's left is for you to enable MangoHud in your game of choice. If you're using Steam, right click on a game and click on ```Properties...```:
![game_properties](/assets/img/2020-07-04-setting-up-mangohud/game_properties.png)

The following window should appear:
![properties_window](/assets/img/2020-07-04-setting-up-mangohud/properties_window.png)


Click on ```SET LAUNCH OPTIONS...``` and the following window should appear:
![launch_options_window](/assets/img/2020-07-04-setting-up-mangohud/launch_options_window.png)

Type the following:
```
mangohud %command%
``` 
and click on ```OK```.

Launch the game and MangoHud will be enabled:
![hitman2_mangohud](/assets/img/2020-07-04-setting-up-mangohud/hitman2_mangohud.jpg)


To toggle it off you can press ```RShift + F12```.