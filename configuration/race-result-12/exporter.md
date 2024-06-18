# Exporter

Exporters need to be created when you want to have IDCamPro react upon the arrival of new passings triggered by new raw data instead of [connecting local to the decoder](../timing/).

In order to receive raw data passings and IDCamPro can act upon them , RR12 exchange needs to define an exporter to send data to us.&#x20;

## Online

Our RemoteRedirect webservice provides a bridge between RR12 working online that can only access public web servers and IDCamPro running locally.&#x20;

{% hint style="info" %}
Protocol is https and host is raceresult.remoteredirect.com:\
`https://raceresult.remoteredirect.com`
{% endhint %}

The following exporter need to be configured in RR12 (Timing - Exporters & Tracking - Exporters):

| URL                                                                                                  | Export Data                                                                                                                      |
| ---------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| <p>HTTP(S) Post</p><p><code>https://raceresult.remoteredirect.com/api/raceresult/exporter</code></p> | <p>Custom</p><p><code>[Event.ID] &#x26; ";" &#x26; [RD_TimingPoint] &#x26; ";"&#x26;[Bib] &#x26; ";" &#x26; [RD_Time]</code></p> |

## Offline

When working offline (e.g. checking out the event and using the local race result Web Server, IDCamPro acts a REST API server to receive exporter data.

{% hint style="info" %}
Protocol is http (not https) and host is localhost:8181 (no www, take care with the :):\
`http://localhost:8182`
{% endhint %}

| URL                                                                                  | Export Data                                                                                                                   |
| ------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| <p>HTTP(S) Post</p><p><code>http://localhost:8182/api/raceresult/exporter</code></p> | <p>Custom<br><code>[Event.ID] &#x26; ";" &#x26; [RD_TimingPoint] &#x26;";"&#x26; [Bib] &#x26; ";" &#x26; [RD_Time]</code></p> |

{% hint style="warning" %}
RRexchange and IDCamPro use different local ports in order to be able to run side-by-side on the same computer.
{% endhint %}

## Online & Offline

_Name_ can be defined as you like, e.g. RRExchange. _Timing Point/Split_ and _Filter_ can be set to whatever you need, however you can always filter in RRExchange as well - so best is to leave it on _All_.&#x20;
