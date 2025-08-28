---
title: Supported Applications
layout: home
nav_order: 6
---

## DMTCP Supported Apps:

In general, we try to support all mainstream applications and most
others. The list below provides a sample of commonly used applications
for which we have directly verified support from DMTCP. If your
application does not work with DMTCP, **this is a bug in DMTCP!** We
would appreciate it if you can notify us of such applications, so that
we can work with you on fixing this bug in DMTCP.

**The Closed World Assumption:** The single biggest issue for most
checkpointing packages is the \"closed world assumption\". This concerns
applications that connect with external services. In these cases, we
must add heuristics that know about the external world. Some classic
examples are X Window apps, InfiniBand connections, NSCD (Name Service
Caching Daemon), LDAP (Lightweight Directory Access Protocol),
re-connecting stdin/stdout/stderr to the current terminal device, and so
on. ([see the list below](supportedApps.html#xwindow).) DMTCP gets
around this through heuristics, and DMTCP plugins.

**The Three Generations of DMTCP:**\
DMTCP is now in its third generation, and gains much of its power from
the ability to interact with external resources. Here is a short history
of DMTCP:

1.  First generation: *a single process on a single computer:*\
    This was assumed to be a closed world. Heuristics were added as
    needed when the external world intruded.
2.  Second generation: *distributed processes on a single computer
    cluster:*\
    This was assumed to be a closed world. Heuristics were added as
    needed when the external world intruded.
3.  Third generation: *distributed applications interacting with the
    external world:*\
    Applications were allowed to interact with the external world
    through the implementation of many [a plugins](plugins.html)\-\--
    each one having expertise on how to save and restore an equivalent
    semantic state for a particular external resource. For example, a
    database client can disconnect from the server before checkpoint,
    and reconnect after resume/restart. A database server can delay
    checkpointing until all current transactions have completed.

**Time (rdtsc):** Time presents a special case during restart. Any
counter or timer active since the beginning of a process will consider
the restarted process to be a new process. This can affect the
x86/x86_64 assembly instruction `rdtsc`, which counts the number of
clock cycles since the beginning of the process.

**Three newer non-POSIX Linux system calls:** DMTCP supports three newer
Linux system calls (epoll, eventfd, and signalfd) as of DMTCP
release 1.2.6.

**Work in Progress:** Support for inotify will be provided in a future
release. Please contact us if you have a need for this.

**Some of the commonly used applications supported by DMTCP:**

- Programming Languages: C/C++, Java, Haskell, Lisp, \...
- Parallel Computing: Open MPI, MPICH2, MVAPICH2, Intel® MPI, OpenMP,
  UPC (Unified Parallel C/C++), Cilk, InfiniBand, SLURM and Torque
  resource managers, \... (see [Parallel Computing page](parallel.html))
- Numerical Computing Environments: Matlab, R, Python/Numpy, \...
- Scripting and Shell Languages: Python, Perl, dash/bash/tcsh/zsh,
  screen, \...
- Web/Internet: MySQL, PHP, Firefox (see X Window Apps), Apache, \...
- Text-based Editors: vi/vim/cscope (vim mouse support not available),
  emacs, \...
- [Graphics/X Window Apps]{#xwindow}: Supported with VNC \-- disconnect
  VNC viewer, and then checkpoint VNC server. Reconnect viewer after
  resume/restart.\
  *NOTE: We also support direct checkpointing of graphics applications,
  including 3D graphics based on OpenGL. This uses a [contributed
  pluginThis described here](http://arxiv.org/abs/1312.6650).*
- Not Supported: Statically Compiled Applications (using libc.a instead
  of libc.so). Could be supported through use of trampolines. Please
  contact us if you have an important application.
