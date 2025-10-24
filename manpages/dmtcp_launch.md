---
title: dmtcp_launch
layout: home
parent: Manpage
nav_order: 9
---

# NAME

**dmtcp_launch** \-- launch a process under DMTCP control.

# SYNOPSIS

**dmtcp_launch** \[*OPTIONS*\] *\<command\>* \[*args\...*\]

# DESCRIPTION

**dmtcp_launch** launches a process under DMTCP control.

A typical usage is:\
rm ckpt\_a.out\\_\*.dmtcp \# Remove any stale copies of ckpt image\
dmtcp\_launch \--interval 5 a.out\
dmtcp\_command \--checkpoint \# Execute this in another window\
#Kill the currently running a.out process\
dmtcp\_restart ckpt\_a.out\\_\*.dmtcp

# OPTIONS

## Connecting to the DMTCP Coordinator

**-h**, **\--coord-host** *hostname* (environment variable DMTCP\_COORD\_HOST)

>   Hostname where dmtcp\_coordinator is run (default: localhost)

<!-- -->

**-p**, **\--coord-port** *port* (environment variable DMTCP\_COORD\_PORT)

>   Port where dmtcp\_coordinator is run (default: 7779)

<!-- -->

**\--port-file** *filename*

>   File to write listener port number. (Useful with **\--coord-port
>   0**, which is used to assign a random port)

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

**\--no-coordinator**

>   Execute the process in stand-alone coordinator-less mode.\
>   Use **dmtcp\_command** or **\--interval** to request checkpoints.

<!-- -->

**-i**, **\--interval** *seconds* (environment variable DMTCP\_CHECKPOINT\_INTERVAL)

>   Time in seconds between automatic checkpoints. 0 implies never
>   (manual ckpt only); if not set and no env var, use default value set
>   in dmtcp\_coordinator or dmtcp\_command. Not allowed if **\--join** is
>   specified

## Checkpoint image generation

**\--gzip**, **\--no-gzip** (environment variable DMTCP\_GZIP=\[01\])

>   Enable/disable compression of checkpoint images (default: 1
>   (enabled))\
>   WARNING: gzip adds seconds. Without gzip, ckpt is often \< 1s

<!-- -->

**\--ckptdir** *path* (environment variable DMTCP\_CHECKPOINT\_DIR)

>   Directory to store checkpoint images (default: curr dir at launch)

<!-- -->

**\--ckpt-open-files**

>   Checkpoint open files and restore old working dir. (default: do
    neither)

<!-- -->

**\--checkpoint-open-files**

>   Deprecated. Use **\--ckpt-open-files** instead.

<!-- -->

**\--ckpt-signal** *signum*

>   Signal number used internally by DMTCP for checkpointing (default:
>   12)

<!-- -->

**\--ckpt-signal** *signum*

>   Deprecated. Use **\--ckpt-signal** instead.

## Enable/disable plugins

**\--with-plugin** *plugins* (environment variable DMTCP\_PLUGIN)

>   Colon-separated list of DMTCP plugins to be preloaded with DMTCP.
>   (Absolute pathnames are required.)

<!-- -->

**\--batch-queue**, **\--rm**

>   Enable support for resource managers (Torque PBS and SLURM).
    (default: disabled)

<!-- -->

**\--modify-env**

>   Update environment variables based on the environment on the restart
>   host (e.g., DISPLAY=\$DISPLAY). This can be set in a file
>   dmtcp\_env.txt. (default: disabled)

<!-- -->

**\--disable-alloc-plugin** (environment variable DMTCP\_ALLOC\_PLUGIN=\[01\])

>   Disable alloc plugin (default: enabled).

<!-- -->

**\--disable-dl-plugin** (environment variable DMTCP\_DL\_PLUGIN=\[01\])

>   Disable dl plugin (default: enabled).

<!-- -->

**\--disable-all-plugins** (EXPERTS ONLY, FOR DEBUGGING)

>   Disable all plugins.

## Other options

**\--prefix** *path*

>   Prefix where DMTCP is installed on remote nodes.

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

DMTCP version 3.0.0 of September, 2018.

# COPYRIGHT

See /usr/share/doc/dmtcp-3.0.0/COPYING file.

License LGPLv3+: GNU LGPL version 3 or later
<http://gnu.org/licenses/lgpl.html>.

This program comes with ABSOLUTELY NO WARRANTY. This is free software,
and you are welcome to redistribute it under certain conditions; see
COPYING file for details.
