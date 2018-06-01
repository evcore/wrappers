# wrappers which extend functionality of some regular Linux commands

### installation
1. make sure $PATH contains /usr/local/bin *before* /usr/bin and /bin
2. git clone https://github.com/evcore/wrappers.git
3. copy/move these wrappers into /usr/local/bin/
Result: extended functionality of some regular Linux commands
See also: comment in the wrappers

### find -disk
How many times did you (want to) run an arbitrary command after which you wanted
to find out what changed on disk in the last few minutes?
You probably needed to use a command like:
$ find / -cmin -5 2>/dev/null |grep -Ev '^/(proc|sys|run)'
Well, using my "find" wrapper you can now simply accomplish this using:
$ arbitrary_command
$ find -disk -cmin -5

### virsh resume|console
Did you ever do a "virsh suspend" and some time later "virsh resume"?
If yes, did you notice, the time on the guest wasn't up2date anymore?
Well, I did, and my "virsh" wrapper fixes this issue.
Other than that, this wrapper also fixes the terminal size after a
"virsh console" but *only* if the package "xterm" has been installed.
