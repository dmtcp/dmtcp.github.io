---
title: Manpage
layout: home
nav_order: 9
has_toc: false
---

# NAME

dmtcp - Distributed MultiThreaded Checkpointing

# SYNOPSIS

**dmtcp\_coordinator** \[port\]

**dmtcp\_launch** command \[args\...\]

**dmtcp\_restart** ckpt\_FILE1.dmtcp \[ckpt\_FILE2.dmtcp\...\]

**dmtcp\_command** coordinatorCommand

# DESCRIPTION

**DMTCP** is a tool to transparently checkpointing the state of an
arbitrary group of programs spread across many machines and connected by
sockets. It does not modify the user\'s program nor the operating
system. **MTCP** is a standalone component of DMTCP available as a
checkpointing library for a single process.

# OPTIONS

For each command, the \--help or -h flag will show the command-line
options. Most command line options can also be controlled through
environment variables. These can be set in bash with \"export
NAME=value\" or in tcsh with \"setenv NAME value\".

DMTCP\_CHECKPOINT\_INTERVAL=integer

> Time in seconds between automatic checkpoints. Checkpoints can also
> be initiated manually by typing \'c\' into the coordinator.
> (default: 0, disabled; dmtcp\_coordinator only)

DMTCP\_HOST=string

>   Hostname where the cluster-wide coordinator is running. (default:
>   localhost; dmtcp\_launch, dmtcp\_restart only)

DMTCP\_PORT=integer

>   The port the cluster-wide coordinator listens on. (default: 7779)

DMTCP\_GZIP=(1\|0)

>   Set to \"0\" to disable compression of checkpoint images. (default:
>   1, compression enabled; dmtcp\_launch only) WARNING: gzip adds
>   seconds. Without gzip, ckpt/restart is often less than 1 s

DMTCP\_CHECKPOINT\_DIR=path

>   Directory to store checkpoint images in. (default: ./)

DMTCP\_SIGCKPT=integer

>   Internal signal number to use for checkpointing. Must not be used by
>   the user program. (default: SIGUSR2; dmtcp\_launch only)

# DMTCP\_COORDINATOR

Each computation to be checkpointed must include a DMTCP coordinator
process. One can explicitly start a coordinator through
dmtcp\_coordinator, or allow one to be started implicitly in background
by either dmtcp\_launch or dmtcp\_restart to operate. The address of the
unique coordinator should be specified by dmtcp\_launch, dmtcp\_restart,
and dmtcp\_command either through the \--host and \--port command-line
flags or through the the DMTCP\_HOST and DMTCP\_PORT environment
variables. If neither is given, the host-port pair defaults to
localhost-7779. The host-port pair associated with a particular
coordinator is given by the command-line flags used in the
dmtcp\_coordinator command, or the environment variables then in effect,
or the default of localhost-7779.

The coordinator is stateless and is **not** checkpointed. On restart,
one can use an existing or a new coordinator. Multiple computations
under DMTCP control can coexist by providing a unique coordinator (with
a unique host-port pair) for each such computation.

The coordinator initiates a checkpoint for all processes in its
computation group. Checkpoints can be: performed automatically on an
interval (see DMTCP\_CHECKPOINT\_INTERVAL above); or initiated manually on
the standard input of the coordinator (see next paragraph); or initiated
directly under program control by the computation through the plugin API
(see below).

The coordinator accepts the following commands on its standard input.
Each command should be followed by the \<return\> key. The commands
are:\
l : List connected nodes\
s : Print status message\
c : Checkpoint all nodes\
f : Force a restart even if there are missing nodes (debugging)\
k : Kill all nodes\
q : Kill all nodes and quit\
? : Show this message

Coordinator commands can also be issued remotely using
**dmtcp\_command**.

# EXAMPLE USAGE

1\. In a separate terminal window, start the dmtcp\_coordinator.

>   (See previous section.)
>
>   dmtcp\_coordinator

<!-- -->

2\. In separate terminal(s), replace each command(s) with \"dmtcp\_launch

>   \[command\]\". The checkpointed program will connect to the
>   coordinator specified by DMTCP\_HOST and DMTCP\_PORT. New threads will
>   be checkpointed as part of the process. Child processes will
>   automatically be checkpointed. Remote processes started via *ssh*
>   will automatically checkpointed. (Internally, DMTCP modifies the
>   *ssh* command line to call dmtcp\_launch on the remote host.)
>
>   dmtcp\_launch ./myprogram

<!-- -->

3\. To manually initiate a checkpoint, either run the command below

>   or type \"c\" followed by \<return\> into the coordinator.
>   Checkpoint files for each process will be written to
>   DMTCP\_CHECKPOINT\_DIR. The dmtcp\_coordinator will write
>   \"dmtcp\_restart\_script.sh\" to its working directory. This script
>   contains the necessary calls to dmtcp\_restart to restart the entire
>   computation, including remote processes created via *ssh*.
>
>   dmtcp\_command -c\
>   OR: dmtcp\_command \--checkpoint

<!-- -->

4\. To restart, one should execute dmtcp\_restart\_script.sh, which is

>   created by the dmtcp\_coordinator in its working directory at the
>   time of checkpoint. One can optionally edit this script to migrate
>   processes to different hosts. By default, only one restarted process
>   will be restarted in the foreground and receive the standard input.
>   The script may be edited to choose which process will be restarted
>   in the foreground.
>
>   ./dmtcp\_restart\_script.sh

# DMTCP PLUGIN

The source distribution includes a top-level *plugin* directory, with
examples of how to write a plugin for DMTCP. Plugins allow a
checkpointed application to disconnect from an external resource, and
then reconnect to it at the time of restart. Further examples are in the
*test/plugin* directory. In particular, *test/plugin/applic-initiated*
demonstrates how an application can request a checkpoint under program
control.

The plugin feature adds three new user-programmable capabilities. A
plugin may: add wrappers around system calls; take special actions at
during certain events (e.g. pre-checkpoint, resume/post-checkpoint,
restart); and may insert key-value pairs into a database at restart time
that is then available to be queried by the restarted processes of a
computation. (The events available to the plugin feature form a superset
of the events available with the dmtcpaware interface.) One or more
plugins are invoked via a list of colon-separated absolute pathnames.

dmtcp\_launch \--with-plugin PLUGIN1\[:PLUGIN2\]\...

# DMTCPAWARE API

This API is now deprecated in favor of DMTCP plugins (see above). DMTCP
provides a programming interface to allow checkpointed applications to
interact with dmtcp. In the source distribution, see
dmtcpaware/dmtcpaware.h for the functions available. See
test/dmtcpaware\[123\].c for three example applications. For an example
of its usage, try:

cd test; rm dmtcpaware1; make dmtcpaware1; ./autotest -v dmtcpaware1

The user application should link with libdmtcpaware.so (-ldmtcpaware)
and use the header file dmtcp/dmtcpaware.h.

# RETURN CODE

A target program under DMTCP control normally returns the same return
code as if executed without DMTCP. However, if DMTCP fails (as opposed
to the target program failing), DMTCP returns a DMTCP-specific return
code, rc (or rc+1, rc+2 for two special cases), where rc is the integer
value of the environment variable DMTCP\_FAIL\_RC if set, or else the
default value, 99.

# SEE ALSO

Full documentation is available at the DMTCP home page:
<http://dmtcp.github.io/>\
FAQ: <http://dmtcp.github.io/FAQ.html>\
Plugins:
<https://github.com/dmtcp/dmtcp/blob/master/doc/plugin-tutorial.pdf>\
examples: <https://github.com/dmtcp/dmtcp/tree/master/test/plugin>

# AUTHORS

DMTCP and its standalone single-process component MTCP (MultiThreaded
CheckPointing) were created by the long-term contributors, Jason Ansel,
Kapil Arya, Gene Cooperman, Rohan Garg, Artem Y. Polyakov, Mike Rieker,
Yao Xu, and a series of additional contributors including Alex Brick, Tyler
Denniston, William Enright, Gregory Kerr, Ana-Maria Visan, and others.
For support, see DMTCP home page.
