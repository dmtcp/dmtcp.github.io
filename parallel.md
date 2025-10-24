---
title: Parallel Computing
layout: home
nav_order: 8
---

## Parallel Computing:

There are three particular areas where DMTCP can support your parallel
computing needs:

*Parallel Languages:*
>   Transparent support for parallel languages (MPI, UPC (Unified
>   Parallel C/C++), etc.). These are viewed by DMTCP as just a \"black
>   box\" consisting of distributed processes; DMTCP also supports
>   transparent checkpointing of the ssh connections often used by these
>   languages.

*The Network:*
>   Transparent support for distributed processes over TCP sockets and
>   over InfiniBand.

*Resource Managers (the batch queue):*
>   Support for Checkpoint-Restart for several popular resource managers
>   (e.g., SLURM, Torque).

If DMTCP doesn\'t work for your favorite parallel language, network, or
resource manager, please write to us. (See [\"Contact
Us\"](contactUs.html).)

------------------------------------------------------------------------

## Specific Application Targets:

- **MPI:** Please check the [MANA](https://github.com/mpickpt/mana) project.
- **CUDA:** Please check the [CRAC](https://github.com/xuyao0127/CRAC-early-development) project.
