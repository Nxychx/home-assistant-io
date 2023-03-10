---
title: DTE Energy Bridge
description: Instructions on how to setup DTE Energy Bridge with Home Assistant.
ha_category:
  - Energy
ha_release: 0.21
ha_iot_class: Local Polling
ha_domain: dte_energy_bridge
ha_platforms:
  - sensor
ha_integration_type: integration
---

A sensor platform for the [DTE](https://www.newlook.dteenergy.com/) Energy Bridge. To find out which version of the DTE Energy Bridge sensor you have, find the status LED on your box.

 - If the status LED is on the top, you have a v1.
 - If the status LED is on the front, you have a v2.

<div class='note'>

The firmware of the DTE v2 bridges that started shipping circa mid-2020 will not work with this integration.

You can check if your firmware is still supported by trying accessing `http://{ip_address}:8888/zigbee/se/instantaneousdemand`, and see if
you get a response.

</div>

To enable this sensor, add the following lines to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
sensor:
  - platform: dte_energy_bridge
    ip: 192.168.1.11
```

{% configuration %}
ip:
  description: The IP address of your bridge.
  required: true
  type: string
name:
  description: Name to use in the frontend.
  required: false
  type: string
version:
  description: Hardware version of the sensor.
  required: false
  type: string
  default: 1
{% endconfiguration %}
