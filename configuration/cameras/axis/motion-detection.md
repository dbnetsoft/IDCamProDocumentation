---
description: >-
  Axis cameras can do motion detection on the camera itself and inform IDCamPro
  about this.
---

# Motion Detection

For this to work, Axis camera must be configured as follows

### Setup Motion Detection

* _AXIS Video Motion Detection_ application must be enabled and running. Make sure of this by going to _Settings_ - _Apps_ - _AXIS Video Motion Detection_
* Setup the app according to your needs in terms of sensitivity and regions of interest. The manual for your camera will guide you on this.

### Setup Rules to alert IDCamPro

Axis camera needs to send a trigger to IDcamPro via network. This is done by creating rules on the camera.

* Go to _Settings_ - _System_ - _Events_
* Create a new rule that is triggered by _Motion Detection_
* Action must be created to connect to IDCamPro on the IP address of IDCamPro laptop and port 8889
* The text to send to IDCamPro must be "_motion_" without parantheses

{% hint style="info" %}
IDCamPro also has its own built-in motion detection that works without any camera-side configuration - see [Motion Detection](../motion-detection.md). The two are independent; use whichever suits the camera, usually not both at once.
{% endhint %}
