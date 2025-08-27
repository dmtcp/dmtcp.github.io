---
title: Publications
nav_order: 6
---

# dmtcp_launch \-- start a process under DMTCP control {#dmtcp_launch----start-a-process-under-dmtcp-control align="center"}

#### Kapil Arya, Gene Cooperman, Rohan Garg, et al. {#kapil-arya-gene-cooperman-rohan-garg-et-al. align="center"}

#### September, 2017 {#september-2017 align="center"}

#### Version 2.5.1 {#version-2.5.1 align="center"}

**dmtcp_launch** \-- start a process under DMTCP control.

### Table of Contents

- [Synopsis](index.html#section_1)
- [Description](index.html#section_2)
- [Options](index.html#section_3)
  - [Connecting to the DMTCP Coordinator](index.html#section_4)
  - [Checkpoint image generation](index.html#section_5)
  - [Enable/disable plugins](index.html#section_6)
  - [Other options](index.html#section_7)

[Reporting Bugs](index.html#section_8)

[See Also](index.html#section_9)

[Author](index.html#section_10)

[Version](index.html#section_11)

[Copyright](index.html#section_12)

## [Synopsis]{#section_1}

**dmtcp_launch** \[*OPTIONS*\] \[*args\...*\]

## [Description]{#section_2}

**dmtcp_launch** is a tool to launch an application under DMTCP control.

## [Options]{#section_3}

##### [Connecting to the DMTCP Coordinator]{#section_4}

A typical usage is:\
` rm ckpt_a.out_*.dmtcp # Remove any stale copies of ckpt image`\
`dmtcp_launch --interval 5 a.out`\
`dmtcp_command --checkpoint # Execute this in another window`\
`# Kill the currently running a.out process`\
`dmtcp_restart ckpt_a.out_*.dmtcp `

**-h**, **\--coord-host** *hostname* (environment variable DMTCP_COORD_HOST)
:   Hostname where dmtcp_coordinator is run (default: localhost)

**-p**, **\--coord-port** *port* (environment variable DMTCP_COORD_PORT)
:   Port where dmtcp_coordinator is run (default: 7779)

**\--port-file** filename
:   File to write listener port number. (Useful with **\--coord-port
    0**, which is used to assign a random port)

**-j**, **\--join**
:   Join an existing coordinator, raise error if one doesn\'t already
    exist

**\--new-coordinator**
:   Create a new coordinator at the given port. Fail if one already
    exists on the given port. The port can be specified with
    **\--coord-port**, or with environment variable DMTCP_COORD_PORT. If
    no port is specified, start coordinator at a random port (same as
    specifying port \'0\').

**\--no-coordinator**
:   Execute the process in stand-alone coordinator-less mode.\
    Use **dmtcp_command** or **\--interval** to request checkpoints.

**-i**, **-interval** *seconds* (environment variable DMTCP_CHECKPOINT_INTERVAL)
:   Time in seconds between automatic checkpoints. 0 implies never
    (manual ckpt only); if not set and no env var, use default value set
    in dmtcp_coordinator or dmtcp_command. Not allowed if **\--join** is
    specified

##### [Checkpoint image generation]{#section_5}

**\--gzip**, **\--no-gzip** (environment variable DMTCP_GZIP=\[01\])
:   Enable/disable compression of checkpoint images (default: 1
    (enabled))\
    WARNING: gzip adds seconds. Without gzip, ckpt is often \< 1s

**\--ckptdir** path (environment variable DMTCP_CHECKPOINT_DIR)
:   Directory to store checkpoint images (default: curr dir at launch)

**\--ckpt-open-files**
:   Checkpoint open files and restore old working dir. (default: do
    neither)

**\--checkpoint-open-files**
:   Deprecated. Use **\--ckpt-open-files** instead.

**\--ckpt-signal** signum
:   Signal number used internally by DMTCP for checkpointing (default:
    12)

**\--ckpt-signal** signum
:   Deprecated. Use **\--ckpt-signal** instead.

##### [Enable/disable plugins]{#section_6}

**\--with-plugin** plugins (environment variable DMTCP_PLUGIN)
:   Colon-separated list of DMTCP plugins to be preloaded with DMTCP.
    (Absolute pathnames are required.)

**\--batch-queue**, **\--rm**
:   Enable support for resource managers (Torque PBS and SLURM).
    (default: disabled)

**\--ptrace**
:   Enable support for PTRACE system call for gdb/strace etc. (default:
    disabled)

**\--modify-env**
:   Update environment variables based on the environment on the restart
    host (e.g., DISPLAY=\$DISPLAY). This can be set in a file
    dmtcp_env.txt. (default: disabled)

**\--ib**, **\--infiniband**
:   Enable InfiniBand plugin. (default: disabled)

**\--disable-alloc-plugin** (environment variable DMTCP_ALLOC_PLUGIN=\[01\])
:   Disable alloc plugin (default: enabled).

**\--disable-dl-plugin** (environment variable DMTCP_DL_PLUGIN=\[01\])
:   Disable dl plugin (default: enabled).

**\--disable-all-plugins** (EXPERTS ONLY, FOR DEBUGGING)
:   Disable all plugins.

##### [Other options]{#section_7}

**\--prefix** path
:   Prefix where DMTCP is installed on remote nodes.

**\--tmpdir** path (environment variable DMTCP_TMPDIR)
:   Directory to store temporary files (default:
    \$TMDPIR/dmtcp-\$USER@\$HOST or /tmp/dmtcp-\$USER@\$HOST)

**-q**, **\--quiet** (or set environment variable DMTCP_QUIET = 0, 1, or 2)
:   Skip NOTE messages; if given twice, also skip WARNINGs

**\--help**
:   Print this message and exit.

**\--version**
:   Print version information and exit.

## [Reporting Bugs]{#section_8}

Report bugs to: dmtcp-forum@lists.sourceforge.net\
DMTCP home page: \<http://dmtcp.sourceforge.net\>

## [See Also]{#section_9}

**dmtcp**(1), **dmtcp_coordinator**(1), **dmtcp_launch**(1),
**dmtcp_restart**(1), **dmtcp_command**(1)

## [Author]{#section_10}

See /usr/share/doc/dmtcp-2.5.1/AUTHORS.

## [Version]{#section_11}

DMTCP version 2.5.1 of September, 2017.

## [Copyright]{#section_12}

See /usr/share/doc/dmtcp-2.5.1/COPYING file.

License LGPLv3+: GNU LGPL version 3 or later .

This program comes with ABSOLUTELY NO WARRANTY. This is free software,
and you are welcome to redistribute it under certain conditions; see
COPYING file for details.
