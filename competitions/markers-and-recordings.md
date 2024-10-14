# Markers & Recordings

## Markers

IDCamPro abstracts timing data away into two seperate types of marker:&#x20;

* Bib marker
* Record markers

Bib markers are usually passings from a transponder system or an impulse from a timing device with a bib entered.&#x20;

Record markers are usually impulses from a lightbeam and also passings from a transponder system as a backup.&#x20;

## Recordings

When a new recording is triggered (manually, via passings or via impulses), a new recording is created with a starttime comprising of the current software time. After the last record marker is received and after obeying the timing devices's recording duration, the recording is stoped and the current software clock is noted as the recordings end time. &#x20;
