# TAG Heuer

<figure><img src="https://dbnetsoft.github.io/IDCamProDocumentation/configuration/timingdevices/images/algetiming.png" alt=""><figcaption></figcaption></figure>

TAG Heuer uses a protocol that is shared between many devices (even FDS)

### Configuration <a href="#configuration" id="configuration"></a>

Channels range from 1 to 99, usually being 1 the start and 2 at the finish. The meaning of each setting is described [here](https://dbnetsoft.github.io/IDCamProDocumentation/configuration/timingdevices/).

Manual button impulses are marked with an M in front of the channel number, e.g. M1 for a button push on the first channel.&#x20;

| Key                | Values   | Default     |
| ------------------ | -------- | ----------- |
| Start Channels     | `1`-`99` | `1 M1`      |
| Recording Channels | `1`-`99` | `1 2 M1 M2` |
| Bib Channels       | `1`-`99` | `1 2 M1 M2` |

