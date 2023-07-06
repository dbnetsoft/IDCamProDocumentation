# Timing Devices

## ALGE-Timing

![Overview](images/algetiming.png)

The following devices are supported:

* ALGE-Timy in most programs, e.g. Backup or PC-Timer
* TDC 8000/8001 by selecting ´ALGE-Timing Timy (Backup)´ as timing device

## Configuration

ALGE-Timing channels are from C0 to C9, usually being C0 the start and C1 the finish.
The meaning of each setting is described [here](index.md).

| Key                | Values | Default |
| -        | ----- | ------- |
| Start Channels     | `C0`-`C9` | `C0` |
| Recording Channels | `C0`-`C9` | `C1` |
| Bib Channels | `C0`-`C9` | `C1` |
| Use Rising/Falling Edge | `true`/`false` | `false` |

!!! tip

    Rising/falling edge should be enabled (checked) when expecting longer finish passings close to each other. This way the recording only stops on the last release of the light beam.



