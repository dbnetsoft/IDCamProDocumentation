# Matching between images and markers

IDCamPro has to work with a variety of different clocks:

* Computer clock (that the software uses out of the box)
* Software clock (IDCamPro can use a time different to the computer clock)
* Timing device' clock (should always be synced to GPS but pretty often is not)

All of these clocks may never be exactly the same, therefore IDCamPro cannot really say: "This frame belongs to this passing for bib 5". All IDCamPro can do is say: "This frame was recorded at 12:00, and these are the passings that happen +/- .5s around that time."

The interval around the selected time can be changed in `Config` - `Settings` -  `Matching Bib/Record markers.`Increasing the interval shows more markers at the same time next to a frame, decreasing the value shows less marker.&#x20;

In case no markers can be matched and even no image is visible, this porbably means there isa bigger mismatch between the time of the receiving frames (computer time or software time) and the time of the markers (the timing device's time and delay in sending). In these situations it is good to observe the [synchronisation ](synchronisation.md)section.&#x20;

