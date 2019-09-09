airport-bssid
=============

Connect to a specific wifi network, based off BSSID (mac address of Access Point).

============
usage: ./Build/Release/airport-bssid &lt;ifname&gt; [&lt;bssid&gt;] [&lt;password&gt;]

- Connect to specific wireless network on &lt;ifname&gt; interface, provided by the access point with &lt;bssid&gt; and password &lt;password&gt;.

- If &lt;bssid&gt; and &lt;password&gt; are excluded, a scan of wireless networks from &lt;ifname&gt; interface is performed and a list of wireless networks are returned with ssid, bssid, channel, and signal strength details.

- Forked from https://github.com/qpSHiNqp/airport-bssid 


Notes
-----

MacOS has changed the implementation around BSSID since this was written, 
and in current versions (Mojave, likely earlier ones also) this does not connect to the BSSID you specify.
It will instead trigger a switch to the strongest BSSID with the same ESSID.
However this is often what is wanted, and this tool effects the change **without** apparent network downtime.
(Compare this with 3 seconds of downtime that `networksetup` inflicts when reconnecting to the same ESSID to switch to the best BSSID.)
So if you're fed up with Mac's clumsy BSSID-switch logic and wishing they supported 802.11r fast roaming,
this can be used to make switching a little more seamless.
