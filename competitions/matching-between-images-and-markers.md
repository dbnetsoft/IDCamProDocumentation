# Matching between images and markers

IDCamPro has to work with a variety of different clocks:

* Computer clock (that the software uses out of the box)
* Software clock (IDCamPro can use a time different to the computer clock)
* Timing device' clock (should always be synced to GPS but pretty often is not)

All of these clocks may never be exactly the same, therefore IDCamPro cannot really say: "This frame belongs to this passing for bib 5". All IDCamPro can do is say: "This frame was recorded at 12:00, and these are the passings that happen +/- .5s around that time."

The interval around the selected time can be changed in `Config` - `Settings` -  `Matching Bib/Record markers.`Increasing the interval shows more markers at the same time next to a frame, decreasing the value shows less marker.&#x20;

## Problems

Usually you should follow the rules in the Synchronization section upfront the competition in order to have images and markers at roughly the same timebase. If there still discrepancies, you can also use the time offset functionality in the Camera view.&#x20;

<figure><img src="../.gitbook/assets/image (6).png" alt="" width="262"><figcaption></figcaption></figure>

Adjusting the time shift will change the frames and markers for the selected time instanctly. You will then see that the result will get better.

<figure><img src="../.gitbook/assets/Untitled Project (3).gif" alt="" width="375"><figcaption></figcaption></figure>

