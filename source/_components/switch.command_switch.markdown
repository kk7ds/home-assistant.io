---
layout: component
title: "Command line switch"
description: "Instructions how to have switches call command line commands."
date: 2015-06-10 22:41
sidebar: true
comments: false
sharing: true
footer: true
ha_category: Switch
---


A switch platform that issues specific commands when it is turned on and off. This might very well become our most powerful platform as it allows anyone to integrate any type of switch into Home Assistant that can be controlled from the command line, including calling other scripts!

To enable it, add the following lines to your `configuration.yaml`:

```yaml
# Example configuration.yaml entry
switch:
  platform: command_switch
  switches:
    kitchen_light:
      oncmd: switch_command on kitchen
      offcmd: switch_command off kitchen
      statecmd: query_command kitchen
      value_template: '{% raw %}{{ value == "online" }}{% endraw %}'
```

Configuration variables:

- **switches** (*Required*): The array that contains all command switches.
  - **entry** (*Required*): Name of the command switch. Multiple entries are possible.
    - **oncmd** (*Required*): The action to take for on.
    - **offcmd** (*Required*): The action to take for off.
    - **statecmd** (*Optional*): If given, this command will be run. Returning a result code `0` will indicate that the switch is on.
    - **value_template** (*Optional*): If specified, statecmd will ignore the result code of the command but the template evaluating to `true` will indicate the switch is on.

## {% linkable_title Examples %}

In this section you find some real life examples of how to use this switch.

### {% linkable_title aREST device %}

The example below is doing the same as the [aREST switch](/components/switch.arest/). The commandline tool [`curl`](http://curl.haxx.se/) is used to toogle a pin which is controllable through REST.

```yaml
# Example configuration.yaml entry
switch:
  platform: command_switch
  switches:
    arest_pin4:
      oncmd: "/usr/bin/curl -X GET http://192.168.1.10/digital/4/1"
      offcmd: "/usr/bin/curl -X GET http://192.168.1.10/digital/4/0"
```

### {% linkable_title Shutdown your local host %}

This switch will shutdown your system that is hosting Home Assistant.

<p class='note warning'>
This switch will shutdown your host immediately, there will be no confirmation.
</p>


```yaml
# Example configuration.yaml entry
switch:
  platform: command_switch
  switches:
    Home Assistant system shutdown:
      offcmd: "/usr/sbin/poweroff"
```

### {% linkable_title Control your VLC player %}

This switch will control a local VLC media player ([Source](https://automic.us/forum/viewtopic.php?f=4&t=144)). 


```yaml
# Example configuration.yaml entry
switch:
  platform: command_switch
  switches:
    VLC:
      oncmd: "cvlc 1.mp3 vlc://quit &"
      offcmd: "pkill vlc"
```
