---
title: dmtcp_restart
layout: home
parent: Manpage
nav_order: 9
---

# NAME

**dmtcp_restart** \-- restart processes from given checkpoint images.

# SYNOPSIS

**dmtcp_restart** \[*OPTIONS*\] *ckpt1.dmtcp* \[*ckpt2.dmtcp\...*\]

# DESCRIPTION

**dmtcp_restart** restarts processes from the given checkpoint image
files. Note that DMTCP also writes out a shell script for restarting all
processes. It is written in the current directory of the coordinator by
default.

# OPTIONS

## Connecting to the DMTCP Coordinator

**-h**, **\--coord-host** *hostname* (environment variable DMTCP\_COORD\_HOST)

>   Hostname where dmtcp\_coordinator is run (default: localhost)

<!-- -->

**-p**, **\--coord-port** *port* (environment variable DMTCP\_COORD\_PORT)

>   Port where dmtcp\_coordinator is run (default: 7779)

<!-- -->

**\--port-file** *filename*

>   File to write listener port number. (Useful with **\--port 0**,
>   which is used to assign a random port)

<!-- -->

**-j**, **\--join**

>   Join an existing coordinator, raise error if one doesn\'t already
>   exist

<!-- -->

**\--new-coordinator**

>   Create a new coordinator at the given port. Fail if one already
>   exists on the given port. The port can be specified with
>   **\--coord-port**, or with environment variable DMTCP\_COORD\_PORT. If
>   no port is specified, start coordinator at a random port (same as
>   specifying port \'0\').

<!-- -->

**-i**, **-interval** *seconds* (environment variable DMTCP\_CHECKPOINT\_INTERVAL)

>   Time in seconds between automatic checkpoints. 0 implies never
>   (manual ckpt only); if not set and no env var, use default value set
>   in dmtcp\_coordinator or dmtcp\_command. Not allowed if **\--join** is
>   specified

## Other options

**\--run-as-root**

>   Allow root to run dmtcp\_restart and disable uid checking. (default:
>   disabled)

<!-- -->

**\--no-strict-uid-checking** (environment variable DMTCP\_DISABLE\_UID\_CHECKING)

>   Disable uid checking for the checkpoint image. This allows the
>   checkpoint image to be restarted by a different user than the one
>   that created it.

<!-- -->

**\--ckptdir** *path* (environment variable DMTCP\_CHECKPOINT\_DIR)

>   Directory to store checkpoint images (default: use the same
>   directory used in previous checkpoint)

<!-- -->

**\--tmpdir** *path* (environment variable DMTCP\_TMPDIR)

>   Directory to store temporary files (default:
>   \$TMDPIR/dmtcp-\$USER@\$HOST or /tmp/dmtcp-\$USER@\$HOST)

<!-- -->

**-q**, **\--quiet** (or set environment variable DMTCP\_QUIET = 0, 1, or 2)

>   Skip NOTE messages; if given twice, also skip WARNINGs

<!-- -->

**\--help**

>   Print this message and exit.

<!-- -->

**\--version**

>   Print version information and exit.

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
