---
description: >-
  Axis cameras can do motion detection on the camera itself and inform IDCamPro
  about this.
---

# Motion Detection

For this to work, Axis camera must be configured as follows

### Setup Motion Detection

* _AXIS Video Motion Detection_ application must be enabled and running. Make sure of this by going to Settings - Apps - AXIS Video Motion Detection
* Setup the app according to your needs in terms of sensitivity and regions of interest. The manual for your camera will guide you on this.&#x20;

### Setup Rules to alert IDCamPro

Axis camera needs to send a trigger to IDcamPro via network. This is done by creating rules on the camera.&#x20;

* Go to Settings - System - Events
* Create a new rule that is triggered by _Motion Detection_
* Action must be created to connectto IDCamPro on the IP address of IDCamPro laptop and port 8889
* The text to send to IDCamPro must be "motion"
