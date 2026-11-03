---
description: >-
  IDCam Remote brings cameras at a remote location to your local IDCamPro
  computer over the internet - no VPN, no port forwarding at the venue.
---

# IDCam Remote

{% hint style="warning" %}
**IDCam Remote is currently invitation-only.** To get access, send an email to [info@dbnetsoft.com](mailto:info@dbnetsoft.com) describing your event and how many cameras you want to connect. You will receive your login for the portal and the stream settings for each camera.
{% endhint %}

## What it is for

IDCamPro normally connects to cameras on the same local network. At many events this is not possible: the finish line is kilometres away from the timing office, the camera sits on a mountain or at a remote checkpoint, and the only connectivity is a mobile router or the venue's guest Wi-Fi.

IDCam Remote solves this with a relay in the cloud:

1. The **Axis camera** at the remote location pushes its video stream out to the IDCam Remote service at **idcam.remoteredirect.com**. Because the camera connects outward, it works behind any NAT, firewall or mobile connection - nothing needs to be opened at the venue.
2. **IDCamPro** on your local computer pulls the same stream back from the service, exactly like it would from a camera in the local network.

```
Axis camera  ──RTMP──►  idcam.remoteredirect.com  ──RTSP──►  IDCamPro
(remote site)           (IDCam Remote service)              (your computer)
```

The service does not re-encode anything: the images IDCamPro receives are exactly the ones the camera's encoder produced, at the resolution, frame rate and quality you set on the camera. H.264 and H.265 are both supported.

If the camera's connection drops, which is normal on mobile links, the camera reconnects by itself and IDCamPro continues receiving images once it is back.

## Step 1: Get your stream settings

After you have been invited, sign in to the portal at [https://idcam.remoteredirect.com](https://idcam.remoteredirect.com). Every camera assigned to you has its own card showing:

| Section         | Field          | Used for                                                                     |
| --------------- | -------------- | ---------------------------------------------------------------------------- |
| **Ingest**      | **Server**     | The RTMP server address you enter on the camera                              |
| **Ingest**      | **Stream key** | The key that identifies this camera - keep it private                        |
| **RTSP output** | **URL**        | The address you enter in IDCamPro, including your personal user and password |

Each value has a **Copy** button. Always copy the values from the portal rather than typing them - the stream key in particular must match exactly.

The card also shows whether the camera is currently connected, how much data is arriving, and a live preview, so you can check the camera end before you even start IDCamPro.

{% hint style="info" %}
The browser preview in the portal only works for codecs your browser can decode. H.264 always works; H.265 often shows no preview in the browser, but the stream is still fine and IDCamPro receives it normally.
{% endhint %}

## Step 2: Stream from the Axis camera

Axis cameras publish to IDCam Remote over **RTMP**, using a streaming app installed on the camera itself - no PC is needed at the remote site. Two apps are known to work:

* [**everstra Live**](https://everstra.com/live.html) - free, see the step-by-step guide below
* **CamStreamer** - the CamStreamer App (ACAP) for Axis cameras

{% hint style="warning" %}
Streaming apps split the address into two fields: a **server / stream URL** and a **stream key**. Put each value from the portal into its own field - entering the complete address into the URL field, or the key into the URL field, is the most common reason a camera does not show up. Use `rtmp://` exactly as shown in the portal; do not switch to `rtmps://`.
{% endhint %}

### Using everstra Live

[everstra Live](https://everstra.com/live.html) is a free app for Axis cameras that streams the camera's H.264 video to an RTMP server without re-encoding it. It needs an Axis camera with ACAP support running **AXIS OS 11.11 or later**. Screenshots of every screen mentioned below are on the [everstra Live page](https://everstra.com/live.html).

**Install and license**

1. Download everstra Live from [everstra.com](https://everstra.com/live.html) and install it on the camera under **Apps** in the camera's web interface.
2. Open the app from the camera's Apps page and go to the **License** tab. The license key is free and is activated online with one click (or by e-mail if the camera has no internet access).

**Configure the stream**

1. Go to the **Settings** tab and expand **Stream 1**.
2. In the **STREAM** section:
   * **Stream URL**: paste the **Server** from the IDCam Remote portal.
   * **Stream Key**: paste the **Stream key** from the portal.
   * **Stream name**: a label for yourself, e.g. the name of the camera or location. It is only shown in everstra.
   * **Resolution**: the resolution IDCamPro should receive. Choose it together with the upload speed available at the venue - on a mobile connection, start lower and increase it once the stream is stable.
   * **View Area**: leave at the default to send the full image, or pick a view area defined on the camera to send only a crop of it.
3. In the **AUDIO** section, keep **Silent audio track** (the default). IDCamPro does not use audio.
4. In the **RECONNECT & AUTO-START** section, enable starting the stream automatically when the camera boots and keep automatic reconnect on. This way the camera resumes streaming on its own after a power or network outage, without anyone at the remote site.
5. Click **Save Settings** at the bottom of the page.

**Start and check**

1. Go to the **Stream** tab and start the stream. It shows as **Streaming**, together with the current bitrate and the number of restarts.
2. Within a few seconds the camera's card in the IDCam Remote portal should show it as connected with data arriving.

{% hint style="info" %}
everstra Live can run up to three streams at once. Streams 2 and 3 are not needed for IDCam Remote - leave them unconfigured unless you want to send the same camera somewhere else as well. Each additional stream needs its own upload bandwidth.
{% endhint %}

{% hint style="info" %}
If a stream keeps restarting, the restart count on the **Stream** tab goes up. Usually the bitrate is too high for the connection: lower the **Resolution**, or reduce the bitrate of the camera's stream profile.
{% endhint %}

### Using CamStreamer

Install and license the CamStreamer App on the camera as described by CamStreamer. Then create a new stream:

1. Choose a **custom RTMP** destination (not YouTube, Facebook or another preset).
2. Paste the **Server** from the portal into the server / RTMP URL field.
3. Paste the **Stream key** from the portal into the stream key field.
4. Select resolution, frame rate and bitrate, keeping the bitrate comfortably below the upload speed available at the venue.
5. Audio is not needed for IDCamPro and can be turned off to save bandwidth.
6. Start the stream and enable automatic start, so the camera resumes streaming on its own after a power or network outage.

## Step 3: Add the camera in IDCamPro

On your local computer, add the remote camera like any other network camera:

1. Open the camera settings in IDCamPro and add a new **H.264/RTSP** camera.
2. Set **Type** to **Other**.
3. Paste the **RTSP output URL** from the portal into **Request URI**. The URL already contains your user name and password, so **Host**, **Username** and **Password** can stay empty.
4. Save the settings. The live image of the remote camera appears in IDCamPro.

From here on the camera behaves like a local one: recordings, markers, [Motion Detection](motion-detection.md) and all other camera features work as usual.

{% hint style="info" %}
Images from a remote camera arrive with some delay, depending on the connection at the venue. Use the camera's **Time Shift** setting (see [Cameras](../cameras.md#per-camera-settings)) to align the images with your triggers and passings, and make sure the **Buffer Time** is long enough to cover the delay.
{% endhint %}

## Troubleshooting

| Symptom                                                     | What to check                                                                                                                                                         |
| ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| The portal never shows the camera as connected              | Server and stream key are in the right fields and copied exactly; the camera has internet access; the venue network does not block outgoing connections on port 1935. |
| The camera connects but drops again after a few seconds     | The bitrate is higher than the venue's upload can carry - lower it on the camera.                                                                                     |
| The portal shows data arriving, but IDCamPro shows no image | The RTSP URL was copied completely, including user and password; your local network allows outgoing connections to the RTSP port shown in the URL.                    |
| No preview in the portal, but IDCamPro works                | The camera streams H.265, which your browser cannot display. This is expected.                                                                                        |
| Images in IDCamPro are late compared to the trigger         | Adjust **Time Shift** for this camera and increase **Buffer Time** if needed.                                                                                         |

If you still have trouble, contact [info@dbnetsoft.com](mailto:info@dbnetsoft.com) with the name of the camera as shown in the portal.
