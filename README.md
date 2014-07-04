`script` and `scriptreplay` are part of the `bsdutils` package in Debian and
Ubuntu, `util-linux-ng` in Fedora and `util-linux` in SUSE. They allow to
capture a terminal or script output and replay it, respectively.

This page uses the vt100 emulator by Frank Bi and adds code of my own to read
typescript and timing files to make it possible to replay captured scripts a
web browser.

By adding an upload facility to this it would be possible to have a youtube or
pastebin for terminal sessions. Due to laziness this remains a proof of concept
for now though.

 - This javascript terminal window is 80x24 characters, so it might be
   best to adjust your terminal window to that size as well using the
   following to check:

    $ watch "tput cols; tput lines"

 - Start recording:

    $ SHELL=/bin/sh TERM=vt100 script -t typescript 2> timingfile

 - Do your stuff and when done exit script with `exit`, `logout` or
   ctrl-d.
 - To test how your recorded session looks like, use:

    $ scriptreplay timingfile typescript

 - Enter `timingfile` and `typescript` into form above and hit the play
   button.

