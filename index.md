---
title: DMTCP
layout: home
---

## About DMTCP:

::: section
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
:::

[News](index.html#news) \| [See Also](index.html#seeAlso) \|
[Authors](index.html#authors) \|
[Acknowledgment](index.html#acknowledgment)

::: subtitle
## Announcement!
:::

::: section
We are currently looking for well qualified applicants who are
interested in joining a Ph.D. program in order to do research on
checkpointing with applications to HPC, supercomputing, cloud computing,
security, and other areas. Interested applicants should write to Gene
Cooperman (gene@ccs.neu.edu) at Northeastern University.
:::

::: subtitle
## [News]{#news}
:::

:::::::::::::::::::::::::::::::::::::: section
::: news
\[2019-08-14\]: Upcoming releases:\
:::

           1. A totally revised DMTCP module for support of MPI is
planned (based on MANA; MPI-Agnostic, Network-Agnostic; see [DMTCP
Publications](http://dmtcp.sourceforge.net/publications.html)).\
           2. Longer-term, a DMTCP version 3.0 is being prepared with
new and better features (e.g., user-programmable barriers within a
plugin). If you would like to try it now, see
[Downloads](http://dmtcp.sourceforge.net/downloads.html).

::: news
\[2019-08-14\]: DMTCP 2.6.0 released!
:::

Newer flags for configure:

- Rename \--enable-debug to \--enable-logging
- Add \--enable-debug: \"-Wall -g3 -O0\" (for debugging DMTCP)

Newer flags for dmtcp_restart:

- Add \--debug-restart-pause flag to dmtcp_restart

Bug fixes and enhancements:

- Fixes for glibc versions greater than or equal to 2.24
- Fix deadlock in system() wrapper when the child crashes
- Fix deadlock when a process is forked in the resume phase (issue #691)
- jsocket: Warn user if peer closes socket while draining (issue #701)
- Fix epoll1 test (initialize addrlen for accept()) (#705)
- Fix to correctly calculate Coordinator/Host IP: Affects some
  distributed applications
- Allow restored stack to grow if needed.
- Fix bug in POSIX timer: race condition manifested in
  test/timer.c/Ubuntu-18.04
- Modified InfiniBand plugin for more robust support (primarily of
  interest for MPI)
- The floating point environment (fegetenv()) is now restored on
  restart. (Formerly, only the rounding mode (fegetround()) was
  restored.)
- The current resource limits (rlim_cur) for RLIMIT_NOFILE and
  RLIMIT_STACK are restored if possible.
- Mutex ownership and robust mutexes are now supported if DMTCP is
  configured with \--enable-mutex-wrappers. (However, this configuration
  can also add runtime overhead if mutex operations are called very
  frequently.) \[Thanks to Johannes Stoelp, Laurent Buchard, Pankaj
  Mehta of Synopsys, Inc.\]
- Fix bug if stack grows a lot after a restart.
- Improved support for pty\'s
- util/gdbinit-example added for those who wish to debug DMTCP
  internals.
- Many bug fixes

::: news
\[2017-11-15\]: DMTCP 2.5.2 released!
:::

The small fixes and ehancements of this \"point release\" include:

- All fixes in Release DMTCP-2.4.9 are incorporated in this release.
- An incompatibility of DMTCP with Open MPI 1.10 when using orterun
  (mpirun) was discovered. This does not affect recent versions, such as
  Open MPI 2.x.
- In some rare cases, open files were not properly restored due to a
  use-after-free bug. This is now fixed.
- In some rare cases, one process had created a SysV shared memory
  object, and a different process was assigned to restore it on restart.
  This was not handled correctly, and is now fixed.
- Correctly restore CPU affinities of threads
- Virtualized SysV shared memory keys to avoid race condition on restart
- Fixed logic for checking if relative path to file was a duplicate of
  another existing path
- The NSCD area for name service caching daemon was not handled
  correctly in CentOS 6.8 and later correctly. Fixed now.
- The Linux sched.h include file for scheduling of cores was added to
  satisfy some older Linux distros that needed it for compiling DMTCP.
- Fixed a regression in which \--enable-debug (for verbose debug logs)
  was not being properly written.
- The DMTCP coordinator was displaying a spurious warning, \"Failed to
  find coordinator IP address\", because it did not check for a
  canoncial hostname. A related issue prevented DMTCP from working
  properly on some SUSE/openSUSE distros.

::: news
\[2017-11-14\]: DMTCP 2.4.9 released!
:::

The small fixes and ehancements of this \"point release\" include:

- Fixed a regression causing deleted NFS files to be handled incorrectly
- Fixed handling of glibc for versions greater than glibc-2.24
- Errors and warnings with gcc-7.x are fixed
- A rare bug affecting pthread_cancel, etc., created incorrect pid on
  restart
- man pages fixed: Description section was always describing
  dmtcp_command

::: news
\[2017-09-05\]: DMTCP 2.5.1 released!
:::

This release mostly provides added robustness. Two notable items of
added functionality are:

1.  DMTCP_RESTART_PAUSE and DMTCP_RESTART_PAUSE0 environment variables
    for easier debugging upon initial restart
2.  The \--debug-logs flag was added to dmtcp_launch/dmtcp_restart. One
    can now turn on logging individually for separate plugins, instead
    of only turning it on globally.

An incompatibility of DMTCP with Open MPI 1.10 when using orterun
(mpirun) was discovered. This may also affect some other versions of
Open MPI 1.10. This bug will be fixed in a future release.

Other fixes and enhancements include:

- Fixed an issue when starting multiple DMTCP coordinators on same host
  at approximately the same time
- Fixed issue with PBS scheduler for HPC
- Fixed issue when restarting on a different host with a larger limit on
  the number of open file descriptors
- dmtcp_launch/dmtcp_restart now accept \'\--debug-logs\' flag to
  specify which DMTCP plugins should produce logging information (It
  used to be all or nothing.)
- Improved robustness for IB (InfiniBand) plugin
- Fixed DMTCP_RESTART_PAUSE and DMTCP_RESTART_PAUSE0 environment
  variables for debugging upon restart
- The brk() call was failing on restart on Debian due to overly strict
  assert
- dmtcp_launch was hanging on some RHEL5 and RHEL6 due to deadlock with
  libc low-level locks. Fixed now.
- Updated tls_pid_offset in DMTCP to handle newer GLIBc (versions \>
  2.24)
- Fixed launch of 32-bit binary when forking/execing from a 64-bit
  executable
- Fixed issue that can affect a parent holding a malloc-lock while
  forking
- Fixed issue when a user thread calls \'dmtcp_get_coord_ckpt_dir()\'

::: news
\[2017-01-03\]: DMTCP 2.5.0 released!
:::

This release includes a few new plugins and several bug fixes for
robustness. Some of the highlights include:

- Support for InfiniBand UD (in addition to the more common InfiniBand
  RC).
- Added support for CMA (Cross-Memory Attach): process_vm_readv and
  process_vm_writev
- Improved multi-arch (mixed 32-/64- bit) support.
- Re-added \--enable-fast-restart.
- Added a new commandline option \--with-plugin-32 for dmtcp_launch to
  specify 32-bit plugins in a 64-bit environment.
- Added \--enable-pthread-mutex-wrappers configure flag to enable
  pthread_mutex\_{lock,unlock} wrappers needed for Open MPI.
- Added ability to specify environment file used in the modify-env
  plugin.
- Allow dmtcp_restart to be invoked by root.
- The following new plugins were added:
  - pathvirt: to virtualize filesystem paths.
  - delayresume: for finer-grained control over resuming of user threads
    during resume/restart.

More details are [here](https://github.com/dmtcp/dmtcp/releases).

::: news
\[2017-02-13\]: DMTCP 2.4.8 released!
:::

If you are using a recent Linux kernel or a recent GLIBC library, and
you need to continue to use the 2.4.x branch, then you are recommended
to upgrade to this 2.4.8 release.

- The newest kernels (approximately Linux version 4.0 and later map VDSO
  into memory slightly differently for 32-bit processes running in a
  64-bit Linux. DMTCP was failing to restart for such 32-bit processes.
  This is now fixed.
- dmtcp_dlsym() extended to provide more robust wrapper functions.
- Corner case fixed: signal handlers now restored before plugins
  restart.
- Minor bug fixes.

More details are [here](https://github.com/dmtcp/dmtcp/releases).

::: news
\[2017-01-03\]: DMTCP 2.4.7 released!
:::

If you are using a recent Linux kernel or a recent GLIBC library, and
you need to continue to use the 2.4.x branch, then you are recommended
to upgrade to this 2.4.7 release.

- The newest kernels (approximately Linux version 4.0 and later) map
  vDSO into memory slightly differently for 32-bit processes running in
  a 64-bit Linux. DMTCP was failing to restart for such 32-bit
  processes. This is now fixed.
- In recent versions of GLIBC, libdl/dlerror calls libc/malloc, creating
  an infinite recursion when we interpose using libdl/dlsym. We now
  implement our own dlsym and use it in most cases, thus reducing our
  reliance on libdl.

More details are [here](https://github.com/dmtcp/dmtcp/releases).

::: news
\[2016-12-31\]: DMTCP 2.4.6 released!
:::

Fixed JLOG to work with \'\--enable-debug\' configure flag. A corner
case in handling of InfiniBand was fixed, where two queue pairs were not
connected. More details are
[here](https://github.com/dmtcp/dmtcp/releases).

::: news
\[2016-07-19\]: DMTCP 2.4.5 released!
:::

This now provides more robust handling of mutexes and InfiniBand. An
\'\--enable-pthread-mutex-wrappers\' configure flag was added to enable
pthread_mutex\_{lock,unlock} wrappers needed for Open MPI. A failure to
build on SLES10 was fixed. Restart was fixed in a case where independent
processes had orphaned roots of trees. The signals SIGCANCEL (signal
#32) and SIGSETXID (signal #33) used by NPTL for threads were not being
properly restored on restart. More details are
[here](https://github.com/dmtcp/dmtcp/releases).

::: news
\[2016-05-22\]: DMTCP 2.5.0-rc2 released!
:::

This \"rc\" version (release candidate version) is an a second, early
version of a \"feature release\". This should be reasonably stable, and
is the current recommended version. Back-ports of bug fixes continue to
be supported for the previous DMTCP 2.4.x series. This version, like
rc1, emphasizes more robust handling of InfiniBand, and also adds some
minor enhancements. See the [News
page](https://sourceforge.net/p/dmtcp/news/) for further information.

::: news
\[2016-10-29\]: A DMTCP module for Slurm is coming.
:::

There is now a private fork of Slurm that provides a DMTCP module for
Slurm with tight integration. This will be submitted for inclusion in
the main branch of Slurm. If someone is interested in testing an advance
version, please contact us.

::: news
\[2016-02-11\]: DMTCP 2.5.0-rc1 released!
:::

This \"rc\" version (release candidate version) is an early version of a
\"feature release\". For those who don\'t need the newest features, they
are still recommended to download the latest DMTP 2.4.x version. This
version emphasizes more robust handling of InfiniBand with
`dmtcp_launch --infiniband`. See the [News
page](https://sourceforge.net/p/dmtcp/news/) for further information.

::: news
\[2016-01-14\]: DMTCP 2.4.4 released!
:::

DMTCP now supports InfiniBand UD. (Newer implementations of MPI are now
often configured to use this transport mode.) Additionally, some issues
were fixed concerning: a regression in our support for multi-arch
installations (for a mixture of 32- and 64-bit target applications); a
race appearing after many ckpt-restart cycles (restart of ckpt of
restart of \...); some utilities for plugins from dmtcp.h marked \"FOR
EXPERTS ONLY\" are now supported \"out of the box\"; the modify-env
plugin was extended to support \"dmtcp_env.txt\" files of size up to
12 KB (with warnings for larger files); an improved error message for
\"dmtcp_launch \--no-coordinator\"; and some minor fixes. More details
are [here](https://github.com/dmtcp/dmtcp/releases).

::: news
\[2015-11-25\]: DMTCP 2.4.3 released!
:::

This is a bug fix release. Some issues were fixed concerning: added
support for CMA (Cross-Memory Attach:
process_vm_readv/process_vm_writev); fixed a regression affecting
dmtcp_checkpoint() \[applic-initiated ckpt API\]; fixed a compilation
error on RHEL-5.8; and some smaller bug fixes.

::: news
\[2015-10-15\]: DMTCP 2.4.2 released!
:::

This is a bug fix release. Some issues were fixed concerning:
`./configure --enable-debug`; compiling under clang; interval
checkpointing (`dmtcp_launch --interval`); having `dmtcp_launch --quiet`
pass on the `--quiet` flag when implicitly starting a new coordinator;
when an application mmap\'s /dev/zero; improved support for
`sched_setaffinity()` and friends; a report on tclsh-8.6 and its use of
pthread_atfork(); `on_semget()` and `semctl()`; and a compilation error
for SLES10.

::: news
\[2015-09-02\]: DMTCP 2.4.1 released!
:::

This is primarily a bug fix release. It fixes an issue with
version 2.4.0 and deleted shared memory files. In particular, this can
affect the use of DMTCP with MPI in some circumstances.

::: news
\[2015-07-24\]: DMTCP 2.4.0 released!
:::

This release provides better support for MPI/SLURM integration for Intel
MPI, MVAPICH-2, MPICH-2, and Open MPI; glibc 2.21; and shared-memory
segments. Check the [release
notes](http://sourceforge.net/p/dmtcp/news/2015/08/dmtcp-240-released)
for more details.

::: news
\[2014-07-14\]: DMTCP 2.3.1 released!
:::

This is primarily a bug fix release.

::: news
\[2014-07-03\]: DMTCP 2.3 released!
:::

This is primarily a bug fix release. However, if you are using DMTCP for
the ARM v7 CPU, or if you are using DMTCP either with the InfiniBand
network or with the SLURM batch system, then it is strongly recommended
to upgrade. Check the [release
notes](http://sourceforge.net/p/dmtcp/news/2014/07/dmtcp-23-released)
for more details.

::: news
\[2014-03-20\]: DMTCP 2.2.1 released!
:::

This is a bug fix release. Users relying on
\--enable-unique-checkpoint-filenames configure flag are highly
recommended to upgrade to this release. Check the [release
notes](http://sourceforge.net/p/dmtcp/news/2014/03/dmtcp-221-released)
for more details.

::: news
\[2014-03-14\]: DMTCP 2.2 released!
:::

In this release, the lowest layers have been re-organized and partially
re-written for greater clarity of code and greater maintainability.
Also, users relying on the use of DMTCP with MPI, InfiniBand or the
Torque or SLURM batch queues are strongly advised to upgrade. Check the
[release
notes](http://sourceforge.net/p/dmtcp/news/2014/03/dmtcp-22-released)
for more details.

::: news
\[2014-01-12\]: DMTCP 2.1 released!
:::

This release includes enhancement to the core feature set and some newly
stable plugins. Check the [release
notes](http://sourceforge.net/p/dmtcp/news/2014/01/dmtcp-21-released)
for more details.

::: news
\[2013-10-03\]: DMTCP 2.0 released!
:::

This version 2.0 release represents the future of DMTCP. DMTCP version
2.0 has been re-designed around the concept of plugins. The older DMTCP
version 1.2.x branch will continue to be maintained for bug fixes. Check
the [release
notes](http://sourceforge.net/p/dmtcp/news/2013/10/dmtcp-20-released)
for more details.

::: {onclick="openClose('oldnews')"}
[Older News](index.html#){onclick="return false;"}
:::

:::::::::::: {#oldnews style="display:none"}
::: news
\[2013-08-03\]: DMTCP 1.2.8 released!
:::

This is primarily a bug fix release. It is particularly recommended to
upgrade if you are using DMTCP with the ARM CPU, or if you will compile
DMTCP with a C++11 compiler (e.g. GNU flag -std=c++11). Check the
[release
notes](http://sourceforge.net/p/dmtcp/news/2013/08/dmtcp-128-released)
for more details.

::: news
\[2013-03-13\]: DMTCP 1.2.7 released!
:::

This is primarily a bug fix release. Check the [release
notes](http://sourceforge.net/p/dmtcp/news/2013/03/dmtcp-127-released)
for more details.

::: news
\[2012-07-31\]: DMTCP 1.2.6 released!
:::

Previous release had issues with compilation on older kernels, this
release fixes that. It also contains some changes needed for gcc 4.7.
Check the [release notes](http://sourceforge.net/news/?group_id=194616)
for more details.

::: news
\[2012-05-27\]: DMTCP 1.2.5 released!
:::

Along with numerous bug fixes, this release features support for ARM
processors along with support for epoll/eventfd/signalfd system calls.
Check the [release notes](http://sourceforge.net/news/?group_id=194616)
for more details.

::: news
\[2012-01-23\]: DMTCP 1.2.4 released!
:::

Along with lot of bug fixes, this release focuses on robust treatment of
processes that rapidly create and destroy threads. Users of DMTCP 1.2.3
are highly encouraged to upgrade to this release. Check the [release
notes](http://sourceforge.net/news/?group_id=194616) for more details.

::: news
\[2011-07-22\]: DMTCP 1.2.3 released!
:::

This is primarily a bug-fix release with lots of bug fixes that improve
overall stability. Users of DMTCP 1.2.2 are highly encouraged to upgrade
to this release. Check the [release
notes](http://sourceforge.net/news/?group_id=194616) for more details.

::: news
\[2011-06-22\]: DMTCP 1.2.2 released!
:::

Along with a lot of bug fixes, this release provides support for a
module system allowing users to write their own extension to DMTCP, and
removed dependency on libc.a for building. Check the [release
notes](http://sourceforge.net/news/?group_id=194616) for more details.

::: news
\[2011-03-12\]: DMTCP 1.2.1 released!
:::

Along with a lot of bug fixes, this release provides support for MPICH2
1.3.x (transparently checkpointing MPICH2 under DMTCP), and calling
dmtcpaware API (dmtcpCheckpoint(), etc.) directly from inside a python
session. Check the [release
notes](http://sourceforge.net/news/?group_id=194616) for more details.

::: news
\[2010-11-04\]: DMTCP 1.2.0 released!
:::

This is a semi-major release of DMTCP. The biggest change is the support
for [GNU screen](http://www.gnu.org/software/screen/) sessions. It also
fixes some instabilities in checkpointing Matlab under certain
environments. Also includes numerous bug fixes were implemented as a
part of review of DMTCP sub-systems.
::::::::::::
::::::::::::::::::::::::::::::::::::::

::: subtitle
## [Authors]{#authors}
:::

::: section
DMTCP is currently maintained by [Kapil
Arya](http://www.ccs.neu.edu/home/kapil/), [Gene
Cooperman](http://www.ccs.neu.edu/home/gene/), [Rohan
Garg](http://www.ccs.neu.edu/home/rohgarg/), [Jiajun
Cao](http://www.ccs.neu.edu/home/jiajun/), and Artem Polyakov. The list
of active developers continues to evolve.
:::

::: subtitle
## [Acknowledgment]{#acknowledgment}
:::

::: section
The DMTCP project is partially supported by grants from Intel
Corporation, and from the National Science Foundation under grants
OCI-0960978, ACI-1440788, and OAC-1740218. Any opinions, findings, and
conclusions or recommendations expressed in this material are those of
the author(s) and do not necessarily reflect the views of Intel
Corporation or of the National Science Foundation.
:::

------------------------------------------------------------------------

Click [here for comments.](contactUs.html){.sidebar}

[![SourceForge.net
Logo](http://sourceforge.net/sflogo.php?group_id=96405&type=5){border="0"
height="62" width="210"}](http://sourceforge.net)
::::::::::::::::::::::::::::::::::::::::::::::::
