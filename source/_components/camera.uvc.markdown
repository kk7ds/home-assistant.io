---
layout: component
title: "UVC camera"
description: "Instructions how to integrate UVC switches within Home Assistant."
date: 2016-02-07 22:15
sidebar: true
comments: false
sharing: true
footer: true
logo: unifi_video.jpg
ha_category: Camera
---

The uvc camera platform lets you integrate UVC cameras connected to your [Ubiquiti UniFi Video](https://www.ubnt.com/enterprise/#unifi-video) controller.

To set it up, add the following to our `configuration.yaml` file:

```yaml
camera:
  platform: uvc
  nvr: CONTROLLER_ADDRESS
  port: CONTROLLER_PORT
  key: API_KEY
```

Configuration variables:

- **nvr** (*Required*): The hostname or address of the UnFi video controller
- **port** (*Optional*): The port number of the controller interface (usually 6443)
- **key** (*Required*): A valid API key for the UniFi video controller
