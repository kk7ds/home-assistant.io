---
layout: component
title: "mFi switch"
description: "Instructions how to integrate mFi switches within Home Assistant."
date: 2016-02-07 22:12
sidebar: true
comments: false
sharing: true
footer: true
logo: mfi.jpg
ha_category: Switch
---

The mFi switch platform lets you control switchable attached to your [Ubiquiti mFi](https://www.ubnt.com/enterprise/#mfi) controller.

To set it up, add the following to our `configuration.yaml` file:

```yaml
switch:
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
