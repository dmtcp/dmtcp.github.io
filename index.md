---
title: Home
layout: home
nav_order: 1
---

## About DMTCP:

DMTCP (Distributed MultiThreaded Checkpointing) transparently
checkpoints a single-host or distributed computation in user-space \--
with no modifications to user code or to the O/S. It works on most Linux
applications, including Python, Matlab, R, GUI desktops, MPI, etc. It is
robust and widely used (on Sourceforge since 2007).

Among the applications supported by DMTCP are MPI (various
implementations), CUDA, OpenMP, MATLAB, Python, Perl, R, and many programming
languages and shell scripting languages. With the use of TightVNC, it
can also checkpoint and restart X-Window applications. The OpenGL
library for 3D graphics is supported through a [special
plugin](http://arxiv.org/abs/1312.6650). It also has strong support for
HPC (High Performance Computing) environments, including MPI, SLURM,
InfiniBand, and other components. See
[QUICK-START.md](https://github.com/dmtcp/dmtcp/blob/master/QUICK-START.md)
for further details.

DMTCP supports the commonly used OFED API for InfiniBand and resource managers
(e.g., SLURM). See
[contrib/infiniband/README](https://github.com/dmtcp/dmtcp/blob/master/contrib/infiniband/README)
for more details.

DMTCP supports MPI and CUDA through plugins. See [MANA (for MPI)](https://github.com/mpickpt/mana)
and [CRAC (for CUDA)](https://github.com/xuyao0127/CRAC-early-development) for more details.
