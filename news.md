---
title: News
layout: home
nav_order: 2
---

## News

### \[2025-06-25\]: DMTCP 4.0.0 released!
This is a major release which introduces breaking checkpoint-image format. As such, the checkpoint images are not compatible with older releases. Other fixes include:
- bug-fixes related to corner cases related to initialization.
- bug-fixes to support custom malloc libraries.
- bug-fix related to a regression involving interval checkpointing.
- fixed a regression involving --restartdir.
- support for close\_range system call.
- Logging improvements.

## Changelog:
- Added DmtcpCkptHeader struct by @karya0 in https://github.com/dmtcp/dmtcp/pull/1144
- Fixed readdmtcp.sh and minor cleanup for restore buf handling. by @karya0 in https://github.com/dmtcp/dmtcp/pull/1188
- Check if plugins need to skip nscd regions by @xuyao0127 in https://github.com/dmtcp/dmtcp/pull/1194
- Use static buffer for motherofall. by @karya0 in https://github.com/dmtcp/dmtcp/pull/1193
- Handle applications with user-defined mmap wrappers. by @karya0 in https://github.com/dmtcp/dmtcp/pull/1195
- Fixed a bug in Util::mmap\_fixed\_noreplace by @xuyao0127 in https://github.com/dmtcp/dmtcp/pull/1197
- Coordinator: Fixed interval checkpointing. by @karya0 in https://github.com/dmtcp/dmtcp/pull/1198
- dmtcp\_coordinator --status-file: started/exited by @gc00 in https://github.com/dmtcp/dmtcp/pull/1199
- Fixed IPC\_PRIVATE handling for SysV Shm. by @karya0 in https://github.com/dmtcp/dmtcp/pull/1192
- Fix VirtPidTbl initialization to not rely on getpid. by @karya0 in https://github.com/dmtcp/dmtcp/pull/1200
- Added close\_range test to syscall-tester. by @karya0 in https://github.com/dmtcp/dmtcp/pull/1202
- Several initialization bugfixes by @karya0 in https://github.com/dmtcp/dmtcp/pull/1203
- Logging improvements by @karya0 in https://github.com/dmtcp/dmtcp/pull/1201
- A few bug fixes related to exec and initialization. by @karya0 in https://github.com/dmtcp/dmtcp/pull/1204
- Coord: Fixed epoll\_wait corner case. by @karya0 in https://github.com/dmtcp/dmtcp/pull/1205
- Use linux\_dirent64 type with sys\_getdents64 by @xuyao0127 in https://github.com/dmtcp/dmtcp/pull/1207
- FIxed --restartdir flag by @xuyao0127 in https://github.com/dmtcp/dmtcp/pull/1208
- Bumped version to 4.0.0 and added NEWS. by @karya0 in https://github.com/dmtcp/dmtcp/pull/1209


**Full Changelog**: https://github.com/dmtcp/dmtcp/compare/3.2.0...4.0.0

### \[2025-02-26\]: DMTCP 3.2.0 released!
This minor release includes:
- support for `[vvar\_vclock]` memory regions present on modern kernels.
- bug fix for pthread\_cancel handling.
- bug fix for dlopen(NULL, ...) calls.
- bug fix for thread handling on RISCV.

**Full Changelog**: https://github.com/dmtcp/dmtcp/compare/v3.1.2...3.2.0

### \[2024-10-14\]: DMTCP 3.1.2 released!
A regression in 3.1.1 caused "dmtcp\_launch -i XX ..." to fail.
A commit was created to fix this.

### \[2024-10-08\]: DMTCP 3.1.1 released!
- jalib/jalloc.cpp: bool\_atomic\_dwcas() -- Align the storage buffers for DMTCP internal allocations to 128 bits (16 bytes)
-  This affected primarily ARM64.  128-bit data types must be 16-byte aligned, or the CPU throws a SIGBUS error
- Small number of minor other change, primarily refactoring for maintenance

### \[2024-09-30\]: DMTCP 3.1.0 released!
- Many bug fixes for robustness, performance
- Supports:  x86\_64, aarch64 (ARM64), RISC-V
- Supports 32-bit arm and x86 (but not recently tested; bug reports welcome)
- New flags: --stale-timeout (default: 8 hours) and --timeout (default: none)
- python3 executable is now the standard for DMTCP:
- Obsolete DMTCP plugins removed
- Enhanced use of atomics for internal lock-free data structures
-   (a regresssion fixed for better performance for OpenMP)
- DMTCP tested to support new platforms:
-   MANA ckpt for MPI (release 1.0.0); CUDA ckpt (experimental;
   McMini (Model Checker: MINImal for easy modification)
     (release 1.0.0; experimental branch for deep debugging))
- Enhanced util/gdb-dmtcp-utils.py tools for GDB debugging
- Enhanced tools for debugging user code in GDB after restart
- See NEWS file for further details

### \[2023-07-09\]: DMTCP 3.0 released!
For some time, it has been recommended to use the latest github master branch for new projects using DMTCP.  This release formalizes that status.  At this time, the InfiniBand plugin is deprecated and likely doesn't work.  Further, the DMTCP flag '--no-coordinator' is not currently supported.  It may be brought back to life if important use cases are seen.  AARCH64 support may or may not work.  Please write to developers if needed.  DMTCP now requires C++14.

However, for transparent checkpointing of MPI, please see: https://github.com/mpickpt/mana That project is undergoing intensive testing.  Please write to the developers for the latest status.

There is also a highly experimental branch to support transparent checkpointing of CUDA: https://github.com/DMTCP-CRAC/CRAC-early-development.  Please write to the developers for plans to replace that experimental version.

Major DMTCP enhancements:

- The plugin facility for end users has now been made more flexible.  In particular, a plugin can now declare a PRESUSPEND phase.  See DMTCP [test/plugin/presuspend/]() for an example plugin using presuspend.  See the mpi-proxy-split plugin of the MANA project for a real-world example.

- DMTCP now includes the ability to create an MTCP restart plugin, for use in split processes (see above). The lower-half application can use the MTCP restart plugin to restore the upper half from its checkpoint image.

- The DMTCP key-value database (KVDB) was extended, for use by user plugins.

- A new GDB utility, DMTCP/util/gdb-dmtcp-utils, is provided.  Source this file into GDB when debugging DMTCP or other software.  'gdb-dmtcp-utils' does not depend on DMTCP, and can be used more generally.

Other enhancements and bug fixes:
- Much of the DMTCP coordinator was rewritten to be more flexible, and support the new split process model.
- DMTCP ordered maps were made more efficient.
- Support for Linux Hugepages was added.
- DMTCP supports Microsoft Windows WSL
- New events, RUNNING and THREAD\_RESUME, were added.
- Added DMTCP\_COORD\_WRITE\_CKPT environment variable
- Improved DMTCP logging for use when debugging DMTCP
- DMTCP now simulate vfork using fork.
- Added ability to truncate append-only/RW files on restart.
- Add './configure --disable-dlsym-wrapper' for special cases
- MAP\_FIXED\_NOREPLACE used for safer execution during restart
- Preserving user-requested rlimit across checkpoint-restart
- Fixed SysV msg queue logic
- Fixed freopen logic
- Many smaller bug fixes

### \[2019-08-14\]: DMTCP 2.6.0 released!

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

### \[2017-11-15\]: DMTCP 2.5.2 released!

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

### \[2017-11-14\]: DMTCP 2.4.9 released!

The small fixes and ehancements of this \"point release\" include:

- Fixed a regression causing deleted NFS files to be handled incorrectly
- Fixed handling of glibc for versions greater than glibc-2.24
- Errors and warnings with gcc-7.x are fixed
- A rare bug affecting pthread_cancel, etc., created incorrect pid on
  restart
- man pages fixed: Description section was always describing
  dmtcp_command

### \[2017-09-05\]: DMTCP 2.5.1 released!

This release mostly provides added robustness. Two notable items of
added functionality are:

-  DMTCP_RESTART_PAUSE and DMTCP_RESTART_PAUSE0 environment variables
   for easier debugging upon initial restart
-  The \--debug-logs flag was added to dmtcp_launch/dmtcp_restart. One
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

### \[2017-01-03\]: DMTCP 2.5.0 released!

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

### \[2017-02-13\]: DMTCP 2.4.8 released!

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

### \[2017-01-03\]: DMTCP 2.4.7 released!

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

### \[2016-12-31\]: DMTCP 2.4.6 released!

Fixed JLOG to work with \'\--enable-debug\' configure flag. A corner
case in handling of InfiniBand was fixed, where two queue pairs were not
connected. More details are
[here](https://github.com/dmtcp/dmtcp/releases).

### \[2016-07-19\]: DMTCP 2.4.5 released!

This now provides more robust handling of mutexes and InfiniBand. An
\'\--enable-pthread-mutex-wrappers\' configure flag was added to enable
pthread_mutex\_{lock,unlock} wrappers needed for Open MPI. A failure to
build on SLES10 was fixed. Restart was fixed in a case where independent
processes had orphaned roots of trees. The signals SIGCANCEL (signal
#32) and SIGSETXID (signal #33) used by NPTL for threads were not being
properly restored on restart. More details are
[here](https://github.com/dmtcp/dmtcp/releases).

### \[2016-05-22\]: DMTCP 2.5.0-rc2 released!

This \"rc\" version (release candidate version) is an a second, early
version of a \"feature release\". This should be reasonably stable, and
is the current recommended version. Back-ports of bug fixes continue to
be supported for the previous DMTCP 2.4.x series. This version, like
rc1, emphasizes more robust handling of InfiniBand, and also adds some
minor enhancements. See the [News
page](https://sourceforge.net/p/dmtcp/news/) for further information.

### \[2016-10-29\]: A DMTCP module for Slurm is coming.

There is now a private fork of Slurm that provides a DMTCP module for
Slurm with tight integration. This will be submitted for inclusion in
the main branch of Slurm. If someone is interested in testing an advance
version, please contact us.

### \[2016-02-11\]: DMTCP 2.5.0-rc1 released!

This \"rc\" version (release candidate version) is an early version of a
\"feature release\". For those who don\'t need the newest features, they
are still recommended to download the latest DMTP 2.4.x version. This
version emphasizes more robust handling of InfiniBand with
`dmtcp_launch --infiniband`. See the [News
page](https://sourceforge.net/p/dmtcp/news/) for further information.

### \[2016-01-14\]: DMTCP 2.4.4 released!

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

### \[2015-11-25\]: DMTCP 2.4.3 released!

This is a bug fix release. Some issues were fixed concerning: added
support for CMA (Cross-Memory Attach:
process_vm_readv/process_vm_writev); fixed a regression affecting
dmtcp_checkpoint() \[applic-initiated ckpt API\]; fixed a compilation
error on RHEL-5.8; and some smaller bug fixes.

### \[2015-10-15\]: DMTCP 2.4.2 released!

This is a bug fix release. Some issues were fixed concerning:
`./configure --enable-debug`; compiling under clang; interval
checkpointing (`dmtcp_launch --interval`); having `dmtcp_launch --quiet`
pass on the `--quiet` flag when implicitly starting a new coordinator;
when an application mmap\'s /dev/zero; improved support for
`sched_setaffinity()` and friends; a report on tclsh-8.6 and its use of
pthread_atfork(); `on_semget()` and `semctl()`; and a compilation error
for SLES10.

### \[2015-09-02\]: DMTCP 2.4.1 released!

This is primarily a bug fix release. It fixes an issue with
version 2.4.0 and deleted shared memory files. In particular, this can
affect the use of DMTCP with MPI in some circumstances.

### \[2015-07-24\]: DMTCP 2.4.0 released!

This release provides better support for MPI/SLURM integration for Intel
MPI, MVAPICH-2, MPICH-2, and Open MPI; glibc 2.21; and shared-memory
segments. Check the [release
notes](http://sourceforge.net/p/dmtcp/news/2015/08/dmtcp-240-released)
for more details.

### \[2014-07-14\]: DMTCP 2.3.1 released!

This is primarily a bug fix release.

### \[2014-07-03\]: DMTCP 2.3 released!

This is primarily a bug fix release. However, if you are using DMTCP for
the ARM v7 CPU, or if you are using DMTCP either with the InfiniBand
network or with the SLURM batch system, then it is strongly recommended
to upgrade. Check the [release
notes](http://sourceforge.net/p/dmtcp/news/2014/07/dmtcp-23-released)
for more details.

### \[2014-03-20\]: DMTCP 2.2.1 released!

This is a bug fix release. Users relying on
\--enable-unique-checkpoint-filenames configure flag are highly
recommended to upgrade to this release. Check the [release
notes](http://sourceforge.net/p/dmtcp/news/2014/03/dmtcp-221-released)
for more details.

### \[2014-03-14\]: DMTCP 2.2 released!

In this release, the lowest layers have been re-organized and partially
re-written for greater clarity of code and greater maintainability.
Also, users relying on the use of DMTCP with MPI, InfiniBand or the
Torque or SLURM batch queues are strongly advised to upgrade. Check the
[release
notes](http://sourceforge.net/p/dmtcp/news/2014/03/dmtcp-22-released)
for more details.

### \[2014-01-12\]: DMTCP 2.1 released!

This release includes enhancement to the core feature set and some newly
stable plugins. Check the [release
notes](http://sourceforge.net/p/dmtcp/news/2014/01/dmtcp-21-released)
for more details.

### \[2013-10-03\]: DMTCP 2.0 released!

This version 2.0 release represents the future of DMTCP. DMTCP version
2.0 has been re-designed around the concept of plugins. The older DMTCP
version 1.2.x branch will continue to be maintained for bug fixes. Check
the [release
notes](http://sourceforge.net/p/dmtcp/news/2013/10/dmtcp-20-released)
for more details.

[Older News](index.html#){onclick="return false;"}

### \[2013-08-03\]: DMTCP 1.2.8 released!

This is primarily a bug fix release. It is particularly recommended to
upgrade if you are using DMTCP with the ARM CPU, or if you will compile
DMTCP with a C++11 compiler (e.g. GNU flag -std=c++11). Check the
[release
notes](http://sourceforge.net/p/dmtcp/news/2013/08/dmtcp-128-released)
for more details.

### \[2013-03-13\]: DMTCP 1.2.7 released!

This is primarily a bug fix release. Check the [release
notes](http://sourceforge.net/p/dmtcp/news/2013/03/dmtcp-127-released)
for more details.

### \[2012-07-31\]: DMTCP 1.2.6 released!

Previous release had issues with compilation on older kernels, this
release fixes that. It also contains some changes needed for gcc 4.7.
Check the [release notes](http://sourceforge.net/news/?group_id=194616)
for more details.

### \[2012-05-27\]: DMTCP 1.2.5 released!

Along with numerous bug fixes, this release features support for ARM
processors along with support for epoll/eventfd/signalfd system calls.
Check the [release notes](http://sourceforge.net/news/?group_id=194616)
for more details.

### \[2012-01-23\]: DMTCP 1.2.4 released!

Along with lot of bug fixes, this release focuses on robust treatment of
processes that rapidly create and destroy threads. Users of DMTCP 1.2.3
are highly encouraged to upgrade to this release. Check the [release
notes](http://sourceforge.net/news/?group_id=194616) for more details.

### \[2011-07-22\]: DMTCP 1.2.3 released!

This is primarily a bug-fix release with lots of bug fixes that improve
overall stability. Users of DMTCP 1.2.2 are highly encouraged to upgrade
to this release. Check the [release
notes](http://sourceforge.net/news/?group_id=194616) for more details.

### \[2011-06-22\]: DMTCP 1.2.2 released!

Along with a lot of bug fixes, this release provides support for a
module system allowing users to write their own extension to DMTCP, and
removed dependency on libc.a for building. Check the [release
notes](http://sourceforge.net/news/?group_id=194616) for more details.

### \[2011-03-12\]: DMTCP 1.2.1 released!

Along with a lot of bug fixes, this release provides support for MPICH2
1.3.x (transparently checkpointing MPICH2 under DMTCP), and calling
dmtcpaware API (dmtcpCheckpoint(), etc.) directly from inside a python
session. Check the [release
notes](http://sourceforge.net/news/?group_id=194616) for more details.

### \[2010-11-04\]: DMTCP 1.2.0 released!

This is a semi-major release of DMTCP. The biggest change is the support
for [GNU screen](http://www.gnu.org/software/screen/) sessions. It also
fixes some instabilities in checkpointing Matlab under certain
environments. Also includes numerous bug fixes were implemented as a
part of review of DMTCP sub-systems.
