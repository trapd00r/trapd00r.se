---
layout: post
title: "Radio Playing Daemon"
---

Radio Playing Daemon
--------------------
**RPD** is a daemon that plays radio streams.

*Mplayer* is used for the actual backend, which means that the User is in charge.

Radio Playing Client
--------------------

**RPC** is the application for controlling the Radio Playing Daemon (RPD).

    Usage: rpc [OPTIONS] (ARGS) 

    OPTIONS:
        np      show the currently playing song
        npi     show the currently playing song on one line
        play    play/switch to channel
        list    list all available channels
        fav     add track to the favlist
        shfav   show favorites
        son     turn on sound
        soff    turn off sound
        toggle  toggle playback status, pause/play
        stop    pauses playback. If you really want to stop, use quit
        quit    stops RPD

    EXAMPLES:
        rpc play psy


Installation
------------
First, you'll need a module from CPAN:

{% highlight bash %}
cpan Working::Daemon
{% endhighlight %}

Then grab the 'now playing'-module:

{% highlight bash %}
git clone git://github.com/trapd00r/Mplayer-Stream-NowPlaying.git
cd Mplayer-Stream-NowPlaying
perl Makefile.PL
make
make install
{% endhighlight %}

Now you're ready to install RPD and RPC:
{% highlight bash %}

git clone git://github.com/trapd00r/RPD.git
cd RPD
perl Makefile.PL
make
make install
{% endhighlight %}

Start RPD and *enjoy*.

License
-------
Copyright (C) 2010 Magnus Woldrich

This program is free software; you can redistribute it and/or modify it under
the terms of the GNU General Public License, version 2, as published by the
Free Software Foundation.

