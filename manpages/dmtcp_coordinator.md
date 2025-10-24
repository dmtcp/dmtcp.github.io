---
title: dmtcp_coordinator
layout: home
parent: Manpage
nav_order: 9
---

# NAME

**dmtcp_coordinater** \-- coordinates checkpoints among multiple
processes.

# SYNOPSIS

**dmtcp_coordinater** \[*OPTIONS*\]

# DESCRIPTION

**dmtcp_coordinator** coordinates checkpoints among multiple processes.

# OPTIONS

**-p**, 

>   **\--coord-port** *port* (environment variable DMTCP\_COORD\_PORT)
>   Port to listen on (default: 7779)

<!-- -->

**\--port-file** *filename*

>   File to write listener port number. (Useful with **\--coord-port
>   0**, which is used to assign a random port)

<!-- -->

**\--ckptdir** *path* (environment variable DMTCP\_CHECKPOINT\_DIR)

>   Directory to store dmtcp\_restart\_script.sh (default: ./)

<!-- -->

**\--tmpdir** *path* (environment variable DMTCP\_TMPDIR)

>   Directory to store temporary files (default: env var TMDPIR or /tmp)

<!-- -->

**\--exit-on-last**

>   Exit automatically when last client disconnects

<!-- -->

**\--exit-after-ckpt**

>   Exit automatically after checkpoint is created

<!-- -->

**\--daemon**

>   Run silently in the background after detaching from the parent
>   process.

<!-- -->

**-i**, 

>   **\--interval** *\<val\>* (environment variable
>   DMTCP\_CHECKPOINT\_INTERVAL) Time in seconds between automatic
>   checkpoints (default: 0, disabled)

<!-- -->

**-q**, **\--quiet**

>   Skip copyright notice.

<!-- -->

**\--help**

>   Print this message and exit.

<!-- -->

**\--version**

>   Print version information and exit.

## Commands for Coordinator

**l**: List connected nodes\
**s**: Print status message\
**c**: Checkpoint all nodes\
**i**: Print current checkpoint interval\
(To change checkpoint interval, use dmtcp\_command)\
**k**: Kill all nodes\
**q**: Kill all nodes and quit\
**?**: Show this message\

# REPORTING BUGS

For bug reports or feature requests, please [open an issue on our GitHub page](https://github.com/dmtcp/dmtcp/issues).\
DMTCP home page: <http://dmtcp.github.io>

# SEE ALSO

**dmtcp**(1), **dmtcp\_coordinator**(1), **dmtcp\_launch**(1),
**dmtcp\_restart**(1), **dmtcp\_command**(1)

# AUTHOR

See /usr/share/doc/dmtcp-3.0.0/AUTHORS.

# VERSION

DMTCP version 3.0.0 of November, 2017.

# COPYRIGHT

See /usr/share/doc/dmtcp-3.0.0/COPYING file.

License LGPLv3+: GNU LGPL version 3 or later
<http://gnu.org/licenses/lgpl.html>.

This program comes with ABSOLUTELY NO WARRANTY. This is free software,
and you are welcome to redistribute it under certain conditions; see
COPYING file for details.
