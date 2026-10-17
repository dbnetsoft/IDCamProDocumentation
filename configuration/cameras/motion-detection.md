---
description: >-
  IDCamPro can automatically detect motion in the live camera image and
  start/stop recording accordingly. This page explains how to configure it and
  what each setting means.
---

# Motion Detection

IDCamPro can watch the live camera image itself and automatically start recording as soon as something moves, without needing a trigger or timing device. This is a software feature built into IDCamPro and is available for cameras connected as **H.264/H.265**, **webcam**, or **NDI** - it is not available for MJPEG, ONVIF, DeckLink or File cameras.

{% hint style="info" %}
Axis cameras can alternatively use their own on-camera motion detection, reported to IDCamPro over the network. See [Axis > Motion Detection](axis/motion-detection.md). The two features are independent - use whichever suits the camera, usually not both at once.
{% endhint %}

### How it works

IDCamPro divides the camera image into a grid of cells and watches each cell for a change in brightness compared to a background image that slowly adapts to the scene. A cell counts as "in motion" once enough of its pixels have changed; the whole frame counts as "motion detected" once enough cells are in motion at the same time. Once motion stops, the detected state is still kept for a few seconds before clearing, so a recording does not cut off during brief pauses in movement.

**While "Use Motion Detection" is enabled for a camera, IDCamPro automatically starts recording as soon as motion is detected, and stops recording a few seconds after motion stops** (marked as recording type "Motion Detection"). This is the main purpose of the feature - it is not only a visual aid.

### Opening the settings

Right-click the camera's live preview and choose **Setup Motion Detection** from the context menu. The menu item only appears for cameras of a supported type.

### Settings explained

| Setting              | Explanation                                                                                                                                                                                                                                                                                                                                                                               |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Use Motion Detection | Enables motion detection for this camera. When enabled, IDCamPro automatically records while motion is detected (see above).                                                                                                                                                                                                                                                              |
| Grid Size (X / Y)    | Number of columns (X) and rows (Y) the image is divided into for analysis. Default 10 x 10. More, smaller cells are more precise about _where_ motion happens but each one also reacts more easily to small or very local changes (e.g. an insect crossing in front of the lens); fewer, larger cells need a bigger area to change before they register.                                  |
| Show Motion          | Shows a live overlay on the camera image: cells currently registering motion are highlighted green, and any excluded areas (see below) are highlighted red. This is a visual aid only and does not affect detection itself.                                                                                                                                                               |
| Sensitivity          | How large a brightness change a pixel needs before it counts as "changed". Range 0-1, default 0.50. Closer to **1** = more sensitive (even small changes are enough to register); closer to **0** = less sensitive (only strong changes register). Raise it if slow or subtle movement is not being picked up; lower it if the camera reacts to lighting flicker, shadows or video noise. |
| Threshold            | Fraction of all grid cells (excluding excluded areas) that must be showing motion **at the same time** for the whole frame to count as motion. Range 0-1, default 0.10 (10% of cells). Raise it to require a larger area of movement before triggering (fewer false positives from small objects); lower it to react to smaller movements.                                                |
| Excluded Areas       | One or more rectangles, in camera image pixels (X1/Y1 = top-left corner, X2/Y2 = bottom-right corner), that are ignored by motion detection entirely. Use this to mask out parts of the image with constant background movement that should never trigger a recording, e.g. trees, flags, a scoreboard, or traffic in the background.                                                     |

Each slider and the grid size have a reset button (the circular arrow icon) that restores that value's factory default (Grid Size 10 x 10, Sensitivity 0.50, Threshold 0.10).

### Update Settings

Settings take effect continuously, but after changing values click **Update Settings** to restart detection: this immediately rebuilds the adapting background image and re-applies the excluded areas, instead of waiting for them to catch up on their own.

### Tuning tips

* Start from the defaults (Grid 10 x 10, Sensitivity 0.50, Threshold 0.10) and enable **Show Motion** to see which cells react as things move in front of the camera.
* If detection does not trigger on real movement, raise **Sensitivity** or lower **Threshold**.
* If detection triggers too easily (recordings start from wind, shadows, insects, or lighting changes), lower **Sensitivity**, raise **Threshold**, or add an **Excluded Area** over the offending region.
* After enabling motion detection or clicking **Update Settings**, give the camera a moment - the first few frames are used to (re)build the background image and are ignored.
