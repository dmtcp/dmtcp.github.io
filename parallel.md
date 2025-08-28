---
title: Parallel Computing
layout: home
nav_order: 6
---

## Parallel Computing:

There are three particular areas where DMTCP can support your parallel
computing needs:

*Parallel Languages:*
:   Transparent support for parallel languages (MPI, UPC (Unified
    Parallel C/C++), etc.). These are viewed by DMTCP as just a \"black
    box\" consisting of distributed processes; DMTCP also supports
    transparent checkpointing of the ssh connections often used by these
    languages.

*The Network:*
:   Transparent support for distributed processes over TCP sockets and
    over InfiniBand.

*Resource Managers (the batch queue):*
:   Support for Checkpoint-Restart for several popular resource managers
    (e.g., SLURM, Torque).

If DMTCP doesn\'t work for your favorite parallel language, network, or
resource manager, please write to us. (See [\"Contact
Us\"](contactUs.html).)

------------------------------------------------------------------------

## Specific Application Targets:

- **MPI:** We regularly test on Open MPI and MVAPICH2, but don\'t have
  the resources to frequently test on all implementations or
  configurations of MPI. If DMTCP is not working for your favorite
  setup, please do send us a message in dmtcp-forum (see [\"Contact
  Us\"](contactUs.html) for that and other channels). See below, if you
  run MPI over InfiniBand. Also, see the [FAQ questions on
  MPI](http://dmtcp.sourceforge.net/FAQ.html#mpi).
- **InfiniBand:** Please use the `--infiniband` flag of `dmtcp_launch`
  for InfiniBand support. This will invoke the InfiniBand plugin for
  DMTCP. While MPI/InfiniBand support has been shown to be robust in
  many configurations in release 2.2.1, we are still testing in other
  configurations. Please write to us (see \"Contact Us\" on left) if you
  observe any bugs.
