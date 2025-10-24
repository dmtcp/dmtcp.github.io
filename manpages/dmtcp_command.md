---
title: dmtcp_command
layout: home
parent: Manpage
nav_order: 9
---

# NAME

**dmtcp_command** \-- send a command to the DMTCP coordinator remotely.

# SYNOPSIS

**dmtcp_commmand** \[*OPTIONS*\] *command* \[*command\...*\]

# DESCRIPTION

**dmtcp_command** is a tool to send user commands to the DMTCP
coordinator remotely.

# OPTIONS

**-h**, **\--coord-host** *hostname* (environment variable DMTCP\_COORD\_HOST)

>   Hostname where **dmtcp\_coordinator** is run (default: localhost)

<!-- -->

**-p**, **\--port** *port* (environment variable DMTCP\_PORT)

>   Port where **dmtcp\_coordinator** is run (default: 7779)

<!-- -->

**\--quiet**

>   Skip copyright notice

**\--help**

>   Print this message and exit.

**\--version**

>   Print version information and exit.

## Commands for Coordinator

**-s** **\--status**

>   Print status message

**-c**, **\--checkpoint**

>   Checkpoint all nodes

**-bc**, **\--bcheckpoint**

>   Checkpoint all nodes, blocking until done

**-i**, **\--interval** *\<val\>*

>   Update ckpt interval to \<val\> seconds (0=never)

**-k**, **\--kill**

>   Kill all nodes

**-q**, **\--quit**

>   Kill all nodes and quit

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
