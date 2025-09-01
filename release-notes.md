# Release Notes

The following list only hightlight key changes that need more documentation. \
All other changes are included in the [setup release notes](https://downloads.dbnetsoft.com/idcampro/history.txt).

#### 25.9.1 (2025-09-01)

* Changed to new versioning scheme (year.month.numberofreleaseinmonth)
*   Recording can be disabled until a specified time (e.g. setup in the morning and then only activate recording 20min before scheduled finish)\


    <figure><img src=".gitbook/assets/image (7).png" alt="" width="375"><figcaption></figcaption></figure>

#### 1.0.53 (2024-12-19)

* For performance reasons, the count of matching bibs, frames and records has been removed in each datagrid
* A new warning tab has been added, that allows to find out record markers without matching bib markers to detect lightbeam crossings without any bib.

#### 1.0.49 @ 2024-11-18

*   A list of all recorded frames can be accessed and all frames can be exported in case of syncing issues

    <figure><img src=".gitbook/assets/image.png" alt="" width="353"><figcaption></figcaption></figure>

#### 1.0.46 @ 2024-10-07

*   Log window shows information about passings and impulses, e.g. if it was used for recording or event if the impulse seems to be not synced (which means may not produce images)\


    <figure><img src=".gitbook/assets/image (5).png" alt="" width="294"><figcaption></figcaption></figure>
*   Both bib and record markers grid now shows the number of matching frames - in case it is 0 it means camera was disconnected or time was not synced\


    <figure><img src=".gitbook/assets/image (1) (1) (1).png" alt="" width="203"><figcaption></figcaption></figure>

#### 1.0.41 @ 2024-06-26

* Improved mapping file import
  * Warning when same transponder is assigned multiple times on import
*   Chip file and dynamic chips from RR12 can be periodically, and automatically imported (default is every 5 minutes)\


    <figure><img src=".gitbook/assets/image (2) (1).png" alt="" width="375"><figcaption></figcaption></figure>

#### 1.0.38 @ 2024-05-08

* New option to specify local web server's port (usually 80)
* New option to send manually added times as manual times instead of raw data

<figure><img src=".gitbook/assets/image (1) (1) (1) (1).png" alt="" width="219"><figcaption></figcaption></figure>

#### 1.0.35 @ 2024-03-21

*   Fixed: Matching record and bib markers are not consuming all of the available vertical screen space anymore but is limited to max. two rows and area is scrollable\


    <figure><img src=".gitbook/assets/image (1) (1) (1) (1) (1).png" alt="" width="375"><figcaption></figcaption></figure>
* Added: Time Shift for adjusting passing to finish line image is now conveniently available on the live camera image when hovering over it with the mouse
* Fixed: No more crash when software was closed while Details Window was still open
* Fixed: When using the Details Window, when navigating around sometimes one of the details views showed a white dot instead of the actual image\
