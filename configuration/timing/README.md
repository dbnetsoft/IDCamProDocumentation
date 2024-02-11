# Timing

IDCamPro can connect to one or more timing devices at the same time. Timing devices can be any of the following:

* ALGE-Timing devices, e.g. Timy or TdC8000
* RaceResult devices, e.g. System 5000 or directly to an Exporter
* Tag Heuer devices, e.g. CP540

<figure><img src="https://dbnetsoft.github.io/IDCamProDocumentation/configuration/timingdevices/images/overview.png" alt=""><figcaption></figcaption></figure>

### Details <a href="#details" id="details"></a>

Each timing device can be configured, where as not all settings applay to all kinds of devices.

| Key                     | Explanation                                                                                                                                                                                         |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Start Channels          | Channel ID on which a start time is received                                                                                                                                                        |
| Recording Channels      | Channel IDs on which a recording of the current images is triggered                                                                                                                                 |
| Bib Channels            | Channel IDs on which a bib number should be taken as valid, e.g. when being manually entered on a timing device or from a transponder                                                               |
| Use rising/falling edge | Only valid for ALGE-Timing devices, device will tell the software when to start and stop a recording (needs to be configured on the timing device as well, otherwise the recording will never stop) |
| Recording duration      | Duration on how long a recording will last after being triggered by the Recording Channel                                                                                                           |
