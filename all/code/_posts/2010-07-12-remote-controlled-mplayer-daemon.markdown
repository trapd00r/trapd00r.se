---
layout: post
title : Remote Mplayer Client/Daemon
---

Remote Mplayer Client/Daemon
------------------------------------------


<h2 class="lightblue">
NAME
</h2>

<p>
<h4 class="pink">
  rmcd - remotely control a daemonized Mplayer process
</h4>
</p>

<h2 class="lightblue">
SYNOPSIS
</h2>
      rmcd [OPTION]... [FILE/URI]

<h2 class="lightblue">
DESCRIPTION
</h2>
    rmcd is a mplayer daemon/client - it daemonizes itself, playing
    music/movies/radio stations and waiting for input through the named
    pipe.

    You can send commands, load and play new content whenever you like.

    You can run rmcd on one computer and remotely control it on another,
    fully transparent. It only cares for the presence of the named pipe.

    You can also setup mplayer to stream the content to you, creating a
    solution similar to MPD and their builti-in httpd streaming (except MPD
    does not support video streaming).

    rmcd features a built-in, user configureable, webradio management
    system, functionality for copying the current track to your portable mp3
    player or wherever you prefer, favorizing of tracks and loading of the
    same, now playing information for both local files and streams, along
    other nifty stuff.

<h2 class="lightblue">
OPTIONS
</h2>
<pre class="terminal">
        -l,   --load       play FILE(s)/URI or radio station (see -list)
        -ch,  --chanlist   list available radio channels
        -cm,  --cmd        send COMMAND to a running process (see shortcuts)
        -cl,  --clist      show a list of commands that are supported
        -cp,  --copy       copy TRACK to DESTDIR
        -i,   --info       show now playing information
        -si   --shinfo     show now playing information on single line
        -k,   --kill       kill the running process
        -h,   --help       show the help
        -m,   --man        show the manpage
</pre>

<h3 class="lightblue">
  Shortcuts for often used commands
</h3>
<pre class="terminal">
        -n    --next       next in playlist
        -p    --prev       previous in playlist
        -t,   --toggle     toggle playback
        -s,   --stop       stop playback
        -f    --fullscreen toggle fullscreen
</pre>

<h2 class="lightblue">
ENVIRONMENT
</h2>
The configuration file should be placed in <strong>$XDG_CONFIG_HOME/rmcd/rmcd.conf</strong>

<h2 class="lightblue">
AUTHOR
</h2>
Written by Magnus Woldrich.

<h2 class="lightblue">
REPORTING BUGS
</h2>
Report bugs to trapd00r\@trapd00r.se or use the <a href="http://github.com/trapd00r/rmcd/issues">issue tracker</a>

<h2 class="lightblue">
COPYRIGHT
</h2>
Copyright 2010 Magnus Woldrich. 

License GPLv2: GNU GPL version 2 or later

This is free software: you are free to change and redistribute it. There
is NO WARRANTY, to the extent permitted by law.

<h2 class="lightblue">
SEE ALSO
</h2>

<p>
<a href="http://github.com/trapd00r/RPD">Radio Playing Daemon</a>

and 

<a href="http://github.com/trapd00r/Mplayer-NowPlaying">Mplayer::NowPlaying</a>

which is used for the metadata info.

</p>

<h2 class="pink">
GET IT
</h2>

{%highlight bash%}
git clone git://github.com/trapd00r/Mplayer-NowPlaying.git
cd Mplayer-NowPlaying
perl Makefile.PL
make
su -c 'make install'

git clone git://github.com/trapd00r/rmcd.git
cd rmcd
perl Makefile.PL
make
su -c 'make install'

# Edit the configuration file and move it to $XDG_CONFIG_HOME/rmcd/rmcd.conf:
mkdir -p $XDG_CONFIG_HOME/rmcd
cp rmcd.conf !$

# Start rmcd and load some music
rmcd -l psy

{%endhighlight%}

