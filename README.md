# Home Assistant Blueprints
In early 2022 I started playing with Home Assistant to increase my control over my home's smart devices. I've created a number of automations and scripts and I've started converting relevent ones into blueprints to share. Here is what I've converted so far.

My goal is to create high quality blueprints that ease HA automation significantly. 

## Scripts
| Name / Code | HA Integration | Details |
| --- | --- | --- |
| [Announce Sonos Alarm](https://github.com/Talvish/home-assistant-blueprints/blob/main/script/announce_sonos_alarm.yaml) | [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FTalvish%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fscript%2Fannounce_sonos_alarm.yaml) | Announces when the next alarm is set on the specified Sonos speaker within the requested time period. This is helpful as part of an automation when going to bed so you don't need to use a phone app to see when/if an alarm is set. Additional details [here](https://community.home-assistant.io/t/script-for-sonos-speakers-to-announce-upcoming-alarm/419700). |
| [Play Media](https://github.com/Talvish/home-assistant-blueprints/blob/main/script/play_media.yaml) | [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FTalvish%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fscript%2Fplay_media.yaml) | Plays the specified media with shuffle, repeat and volume options. If you have a multi-room setup (e.g. Sonos) additional media players can be specified. The script will place all players into a group and if a volume is specified it will be applied to all players. Additional details [here](https://community.home-assistant.io/t/play-media-script-w-shuffle-repeat-multi-room-volume-support/415234). |
| [Play Random Media](https://github.com/Talvish/home-assistant-blueprints/blob/main/script/play_random_media.yaml) | [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FTalvish%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fscript%2Fplay_random_media.yaml) | This is the same as `Play Media` except you can specify a list of media content ids that the script will randomly choose from whenever the script is invoked. Additional details [here](https://community.home-assistant.io/t/play-random-media-script-w-shuffle-repeat-multi-room-volume-support/426445). |
| [Sonos Say](https://github.com/Talvish/home-assistant-blueprints/blob/main/script/sonos_say.yaml) | [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FTalvish%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fscript%2Fsonos_say.yaml) | Uses Text-to-Speech to play a message on Sonos speakers. The script handles oddities I've observed including handling Sonos saving/restore state, handling speaker groups, pausing music, managing volume, disabling repeat, etc. Additional details [here](https://community.home-assistant.io/t/script-for-sonos-speakers-to-do-text-to-speech-and-handle-typical-oddities/424842). |
| [Stop Sonos Alarm](https://github.com/Talvish/home-assistant-blueprints/blob/main/script/stop_sonos_alarm.yaml) | [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FTalvish%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fscript%2Fstop_sonos_alarm.yaml) | Stops current audio on the specified Sonos speaker but if nothing is playing the script checks if an alarm is coming soon and if so, prevents it from going off by disabling the alarm and then re-enabling after it would have gone off. Only one alarm is impacted. This is perfect for when you wake up earlier than your alarm and don't want the alarm to wake others. Additional details [here](https://community.home-assistant.io/t/script-for-sonos-speakers-to-stop-current-alarm-or-temporarily-disable-upcoming-alarm/417610). |

&nbsp;
## Automations

| Name / Code | HA Integration | Details |
| --- | --- | --- |
| [Sonos Sleep /  Alarm Handler](https://github.com/Talvish/home-assistant-blueprints/blob/main/automation/sonos_sleep_handler.yaml) | [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FTalvish%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fautomation%2Fsonos_sleep_handler.yaml) | Listens for a button press and depending on when, will either disable an upcoming alarm and run a configurable action, or will announce the next alarm, play sleep music and run a configurable action. This uses a variety of the script blueprints found above. Additional details [here](https://community.home-assistant.io/t/automation-for-sonos-lutron-picos-to-magically-manage-sleep-alarms-and-music/426477).|
| [Automatic Timed Turn Off](https://github.com/Talvish/home-assistant-blueprints/blob/main/automation/timed_turn_off.yaml) | [![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FTalvish%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fautomation%2Ftimed_turn_off.yaml) | Automatically turns off the specified switch after a given time period whenever the specified switch is turned on. This was my equivalent of `hello world` to figure out how to create blueprints.  |
