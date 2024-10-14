# Synchronisation

The timing device has it's own timebase and the computer has it's own clock (Windows).&#x20;

It is best to first check how big the dfifference is between the windows computer clock and the timing device:

1. First right-click on the clock in the lower right corner and select Sync.&#x20;
2. When you create passings, you will see the difference to computer time the user interface. Any value higher than .5s should be compensated. Make some more passings and see if the difference is always almost identical - if not syncing will not yield good results.&#x20;
3. Now tick the check box and make another passing. Now the software's internal clock is synced and bypasses the windows clock.&#x20;
4. Makes some more passings. The difference should now be well within .1s&#x20;

{% embed url="https://www.youtube.com/watch?v=xiCicV9Ew2w" %}
