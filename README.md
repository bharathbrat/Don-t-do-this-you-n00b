# Don’t do this you n00b!

An effort to capture some common mistakes n00b DevOps / SysAd (Anyone who f'd up on a shell) will do, which will hopefully lead to avoiding these mistakes. Please attach relevant incidents to show what was the effect. :-)

* If you have the habit of shutting down your system using “sudo poweroff” etc. STOP! At the end of the day when you want to go home, imagine running “sudo poweroff” thinking it is your system but it happens on a production system. You could end up going home forever if you choose the right production system. (I urge you not to!).

* *DO NOT* put scripts you write on Github or any public place without first sanitizing it. Related incident being: [People have uploaded AWS keys](https://wptavern.com/ryan-hellyers-aws-nightmare-leaked-access-keys-result-in-a-6000-bill-overnight) and it has been misused. There are bots/scripts that are always on the lookout for these type of keys.

* Do not use public pastebins available to share critical data.

* When trying to start/stop/restart a bunch of services using a for loop; re-check for spaces. /etc/init.d has halt which takes no arguments and shuts down the system.
Example: ```for i in `ls /etc/init.d/ redis-*`; do sudo $i status; done``` will shutdown the system
P.S: Don’t run the above code you *n00b!*
