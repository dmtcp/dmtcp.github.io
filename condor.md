---
title: Condor Integration
nav_order: 5
---

:::: cell
## Condor Integration:

**IMPORTANT: We have a report that the script below is not compatible
with Condor version 8 and the latest DMTCP. We will be updating our
pointer to a canonical script that supports Condor-8/DMTCP. If you use
Condor-8, please check back here later.**

[Condor](http://research.cs.wisc.edu/condor/) is a system to support
high throughput computing. It is free and open source. The Condor
standard universe supports a Condor-specific checkpoint-restart feature
for long-running jobs. But the standard universe is too restrictive for
some users. (For example, it does not support multi-threaded processes.)

The Condor Vanilla Universe supports most types of programs, including
multi-threaded, multi-process, etc. But it does not natively support
checkpoint-restart.

In joint work with the Condor team, we support checkpoint-restart for
the Condor Vanilla Universe, thus providing the best of both worlds
(vanilla universe + checkpoint-restart). The Condor distribution
includes a *shim script (shim_dmtcp)* to interface between Condor and
DMTCP. This [web
page](https://htcondor-wiki.cs.wisc.edu/index.cgi/wiki?p=DmtcpCondor)
will guide you on how to register with Condor and then download the shim
script. For the user\'s convenience, we also provide

- a [copy of the shim script (shim_dmtcp) here](docs/shim_dmtcp).

Finally, we provide a pdf document,

- [condor-dmtcp-overview.pdf](docs/condor-dmtcp-overview.pdf),

to help introduce you to how to use Condor with shim_dmtcp, in order to
use DMTCP-based checkpoint-restart with the Condor Vanilla Universe. If
you are already familiar with Condor, you can probably read the first
page, and then skip to the appendix for the sample submit description
file.

**Debian 6.0:** Please note that a bug report has been filed for
Debian 6.0. This bug prevents the integration of Condor/DMTCP/Debian. A
full description, and a *workaround* is described on this Condor wiki
page:

- [HTCondorWiki: Ticket
  #3094](https://htcondor-wiki.cs.wisc.edu/index.cgi/tktview?tn=3094)

------------------------------------------------------------------------

Click [here for comments.](contactUs.html){.sidebar}

[![SourceForge.net
Logo](http://sourceforge.net/sflogo.php?group_id=96405&type=5){border="0"
height="62" width="210"}](http://sourceforge.net)
:::
