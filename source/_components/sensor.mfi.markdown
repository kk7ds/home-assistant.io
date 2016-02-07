---
layout: component
title: "mFi sensor"
description: "Instructions how to integrate mFi sensors within Home Assistant."
date: 2016-02-07 17:15
sidebar: true
comments: false
sharing: true
footer: true
logo: mfi.jpg
ha_category: Sensor
---

The mFi sensor platform lets you view data from sensors attached to your [Ubiquiti mFi](https://www.ubnt.com/enterprise/#mfi) controller.

To set it up, add the following to our `configuration.yaml` file:

```yaml
sensor:
  platform: mfi
  host: CONTROLLER_ADDRESS
  port: CONTROLLER_PORT
  username: YOUR_USERNAME
  password: YOUR_PASSWORD
```

Configuration variables:

- **host** (*Required*): The hostname or address of the mFi controller
- **port** (*Optional*): The port number of the controller interface (usually 6443)
- **username** (*Required*): The username of the mFi admin user
- **password** (*Required*): The password for the mFi admin user
