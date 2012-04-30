These two scripts, `iridium-calendar` and `iss-calendar`, scrape satellite viewing information from the [Heavens Above][1] website and add it to iCal. Their purpose is to give you notice of good satellite viewing opportunities (weather permitting).

Both scripts require

1. That you are a registered Heavens Above user with a username and password.
2. That you have set an observing site (a latitude/longitude pair) at Heavens Above.
3. That you've created a `.heavens-above` dotfile in your home directory. The contents of the file should consist of one line of text with your username and password, separated by a colon. For example:

        drdrang:p455w0rd

    A single `.heavens-above` dotfile works for both scripts.
4. Two non-standard Python libraries: Kenneth Reitz's [envoy][2], and Crummy Software's [Beautiful Soup][7].

The `iridium-calendar` script gets a week's worth of [Iridium satellite flares][3]. These are brief, bright reflections off the polished antennas of one of the 66 [Iridium communications satellites][4].

The `iss-calendar` script gets a week's worth of [International Space Station][5] passes. These are bright but otherwise conventional satellite passes that last a few minutes.

Each script has a personalization section in which the user can set parameters that filter out less interesting (e.g., less bright) events and can tell the script which iCal calendar to put the notices in.

An alarm is set for 15 minutes before the event, giving the user time to get outside.

The scripts are intended to be run automatically each week via OS X's [launchd mechanism][6] or [cron][8].

If you simply want a list of the next week's worth of events, you can run the scripts from the command line with the `-p` option. This will print the dates, times, location, and brightness for each event, one per line.


[1]: http://heavens-above.com
[2]: https://github.com/kennethreitz/envoy
[3]: http://en.wikipedia.org/wiki/Satellite_flare#Iridium_satellite_flare
[4]: http://en.wikipedia.org/wiki/Iridium_satellite_constellation
[5]: http://en.wikipedia.org/wiki/International_Space_Station
[6]: https://developer.apple.com/library/mac/#documentation/Darwin/Reference/Manpages/man8/launchd.8.html
[7]: http://www.crummy.com/software/BeautifulSoup/
[8]: http://en.wikipedia.org/wiki/Cron
