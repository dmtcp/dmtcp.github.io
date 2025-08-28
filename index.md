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
implementations), OpenMP, MATLAB, Python, Perl, R, and many programming
languages and shell scripting languages. With the use of TightVNC, it
can also checkpoint and restart X-Window applications. The OpenGL
library for 3D graphics is supported through a [special
plugin](http://arxiv.org/abs/1312.6650). It also has strong support for
HPC (High Performance Computing) environments, including MPI, SLURM,
InfiniBand, and other components. See
[QUICK-START.md](https://github.com/dmtcp/dmtcp/blob/master/QUICK-START.md)
for further details.

DMTCP supports the commonly used OFED API for InfiniBand, as well as its
integration with various implementations of MPI, and resource managers
(e.g., SLURM). See
[contrib/infiniband/README](https://github.com/dmtcp/dmtcp/blob/master/contrib/infiniband/README)
for more details.

## Announcement!

We are currently looking for well qualified applicants who are
interested in joining a Ph.D. program in order to do research on
checkpointing with applications to HPC, supercomputing, cloud computing,
security, and other areas. Interested applicants should write to Gene
Cooperman (gene@ccs.neu.edu) at Northeastern University.

## Authors

DMTCP is currently maintained by [Kapil
Arya](http://www.ccs.neu.edu/home/kapil/), [Gene
Cooperman](http://www.ccs.neu.edu/home/gene/), [Rohan
Garg](http://www.ccs.neu.edu/home/rohgarg/), [Jiajun
Cao](http://www.ccs.neu.edu/home/jiajun/), and Artem Polyakov. The list
of active developers continues to evolve.

## Acknowledgment

The DMTCP project is partially supported by grants from Intel
Corporation, and from the National Science Foundation under grants
OCI-0960978, ACI-1440788, and OAC-1740218. Any opinions, findings, and
conclusions or recommendations expressed in this material are those of
the author(s) and do not necessarily reflect the views of Intel
Corporation or of the National Science Foundation.