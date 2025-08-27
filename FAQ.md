---
title: Frequently Asked Questions
nav_order: 1
---

::::::::: cell

- [**I. General Questions**](FAQ.html#sect-general)
- [**II. Support for Specific Types of Software
  Applications**](FAQ.html#sect-targetApps)

------------------------------------------------------------------------

- [**I. General Questions**](FAQ.html#general){#sect-general}
  - [Basics](FAQ.html#basics)
    1.  [How does one run DMTCP?](FAQ.html#runningDMTCP)
    2.  [What types of programs can DMTCP
        checkpoint?](FAQ.html#progType)
    3.  [What is the license for DMTCP?](FAQ.html#license)
    4.  [Do I need to re-compile or re-link my applications to use
        DMTCP?](FAQ.html#compile)
    5.  [Do I need to add kernel modules or patch my
        kernel?](FAQ.html#kernelMod)
  - [Use Cases](FAQ.html#uses)
    1.  [How does one use DMTCP for a distributed computation (for
        example, on a cluster)?](FAQ.html#cluster)
    2.  [](FAQ.html#cluster) [Can I migrate my applications (restart on
        another host, possibly with a different Linux); and what if I
        see a message `illegal instruction`?](FAQ.html#migrate)
    3.  [How can my software invoke a checkpoint or restart directly
        under control of my program?](FAQ.html#dmtcpaware)
    4.  [What is the exit code (return status) for a target application
        running under DMTP?](FAQ.html#exitcode)
    5.  [Does DMTCP support third-party plugins (add-ons) to change the
        behavior of DMTCP at run-time?](FAQ.html#plugins)
    6.  [On restart, a process sees only the environment variables from
        the time of checkpoint (since DMTCP restores the previous
        memory). What do I do if I want to see the newest environment
        values at the time of restart?](FAQ.html#modifyEnv)
    7.  [What if my target application runs as root, uses the setuid
        bit, uses capabilities, or uses other special
        privileges?](FAQ.html#root)
    8.  [](FAQ.html#root) [What if my target application runs as root,
        uses the setuid bit, uses capabilities, or uses other special
        privileges?](FAQ.html#root)
    9.  [](FAQ.html#root) [How can I read a summary of the contents of a
        DMTCP checkpoint image?](FAQ.html#readdmtcp)
    10. [How do I debug my application under GDB when I am using
        DMTCP?](FAQ.html#debugging)

    [](FAQ.html#debugging)
  - [](FAQ.html#debugging) [Architectures Supported by
    DMTCP](FAQ.html#architectures)
    1.  [What CPUs has DMTCP been ported to?](FAQ.html#cpuPorts)
    2.  [How can I compile DMTCP for mixed x86/x86_64 architectures
        (multi-arch/multilib: mixed 32-/64-bit)?](FAQ.html#intel32-64)
    3.  [What operating systems has DMTCP been ported
        to?](FAQ.html#osPorts)
    4.  [What types of networks does DMTCP
        support?](FAQ.html#networkPorts)
    5.  [What Linux distributions do you test on?](FAQ.html#distros)
  - [Performance](FAQ.html#performance)
    1.  [My application takes several seconds (or longer) to checkpoint
        and restart. What can I do to speed it up?](FAQ.html#speed)
    2.  [](FAQ.html#speed) [Can I tell DMTCP that some of my memory does
        not need to be checkpointed (specifying *cutouts*, for a smaller
        checkpoint image)?](FAQ.html#size)

    [](FAQ.html#size)
  - [](FAQ.html#size) [DMTCP Internals](FAQ.html#internals)
    1.  [How does DMTCP work?](FAQ.html#internalWorking)
    2.  [Is there documentation on the internals of
        DMTCP?](FAQ.html#documentation)
    3.  [Can I enable tracing of DMTCP internals?](FAQ.html#jassert)
    4.  [I suspect a bug concerning an interaction with an internal
        plugin of DMTCP. How can I debug this?](FAQ.html#debugPlugins)
    5.  [What is the run-time overhead of
        DMTCP?](FAQ.html#internalOverhead)
    6.  [What O/S features are supported by DMTCP?](FAQ.html#osFeatures)
  - [About the DMTCP Project](FAQ.html#dmtcpProject)
    1.  [Who should I write to for support?](FAQ.html#supportContact)
    2.  [When was work on DMTCP begun, and who works on it
        now?](FAQ.html#history)
    3.  [How should I cite DMTCP in a publication?](FAQ.html#citeDMTCP)
- [**II. Support for Specific Types of Software
  Applications**](FAQ.html#targetApps){#sect-targetApps}
  - [What Applications does DMTCP Support?](FAQ.html#supportedApps)
    1.  [Is there a simple, general description of what applications are
        supported?](FAQ.html#generalSupport)
    2.  [Does DMTCP support multi-threaded and distributed
        programs?](FAQ.html#distributed)
    3.  [Does DMTCP support Java?](FAQ.html#javaSupport)
    4.  [Does DMTCP support checkpointing of
        Matlab?](FAQ.html#matlabSupport)
    5.  [Does DMTCP support checkpointing of R programs (for statistical
        computing)?](FAQ.html#RCkpt)
    6.  [Does DMTCP support MPI?](FAQ.html#mpiSupport)
    7.  [Does DMTCP support multi-threaded languages such as OpenMP and
        Cilk?](FAQ.html#openmpSupport)
    8.  [Does DMTCP support integration with batch queues (resource
        managers)?](FAQ.html#batchQueue)
    9.  [Does DMTCP support integration with
        Condor?](FAQ.html#batchQueue)
    10. [Does DMTCP support GNU screen?](FAQ.html#screenSupport)
    11. [Can DMTCP checkpoint a GDB session?](FAQ.html#gdb)
    12. [Does DMTCP support X-Windows graphics (GUI)
        programs?](FAQ.html#xwindowsSupport)
  - [Checkpointing Matlab](FAQ.html#matlab)
    1.  [Does DMTCP support checkpointing of Matlab
        programs?](FAQ.html#matlabCkpt)
  - [Checkpointing MPI](FAQ.html#mpi)
    1.  [Does DMTCP support checkpointing of MPI
        programs?](FAQ.html#mpiCkpt)
    2.  [Does DMTCP support MPI for InfiniBand, Myrinet, or
        iWARP?](FAQ.html#mpiInfiniBand)
    3.  [What types of batch queues (resource managers) does DMTCP
        support?](FAQ.html#batchQueuePorts)

If you don\'t see your question here, consider [searching within the
archive of past dmtcp-forum
messages](http://sourceforge.net/p/dmtcp/mailman/search/?mail_list=dmtcp-forum),
or else asking your question directly (see \"Contact Us\" on the left).\

------------------------------------------------------------------------

::: faqHeader
[**I. General Questions**]{#general}
:::

- ::: faqHeader
  [Basics]{#basics}
  :::

  1.  ::: faq
      [How does one run DMTCP?]{#runningDMTCP}
      :::

      ` % dmtcp_launch ./a.out arg1 arg2 ...`\
      `% dmtcp_command --checkpoint     [from another terminal window on same computer]`\
      `% dmtcp_restart ckpt_a.out_*.dmtcp`\
      If using the above recipe, make sure to first remove old ckpt
      images. DMTCP also writes out `./dmtcp_restart_script.sh`, which
      handles various bookkeeping and is safer to use.\
      *NOTE:* Numerous configure and run-time options are also
      available.

  2.  ::: faq
      [What types of programs can DMTCP checkpoint?]{#progType}
      :::

      It checkpoints most binary programs on most Linux distributions.
      Some examples on which users have verified that DMTCP works are:
      Matlab, R, Java, Python, Perl, Ruby, PHP, Ocaml, GCL (GNU Common
      Lisp), emacs, vi/cscope, Open MPI, MPICH-2, MVAPICH2, Intel® MPI,
      OpenMP, and Cilk. Both TCP and InfiniBand connections are
      supported. See [Supported Applications](supportedApps.html) for
      further details. Our goal is to support DMTCP for all vanilla
      programs. If DMTCP does not work correctly on your program, **then
      this is a bug in DMTCP**. We would be appreciative if you can then
      [file a bug report with DMTCP](contactUs.html).

  3.  ::: faq
      [What is the license for DMTCP?]{#license}
      :::

      It is a free software distributed under the terms of the [Lesser
      GNU Public License (LGPL)](http://www.gnu.org/licenses/lgpl.html).
      This license was chosen to be *non-contagious*. If you distribute
      a modified version of DMTCP, you must make available to your users
      your modifications to DMTCP. But proprietary or other software may
      freely use the DMTCP libraries and utilities with no restrictions
      on the proprietary or other software.

  4.  ::: faq
      [Do I need to re-compile or re-link my applications to use
      DMTCP?]{#compile}
      :::

      No. DMTCP is completely transparent in this sense.

  5.  ::: faq
      [Do I need to add kernel modules or patch my kernel?]{#kernelMod}
      :::

      No. DMTCP requires no root permissions. Hence, other software
      packages can easily include DMTCP as part of their distribution
      (subject to [DMTCP\'s LGPL license](FAQ.html#license)). (See also
      [*setuid and other special privileges*](FAQ.html#root).)

  ::: faqHeader
  [Use Cases]{#uses}
  :::

  1.  ::: faq
      [How does one use DMTCP for a distributed computation (for
      example, on a cluster)?]{#cluster}
      :::

      A DMTCP computation consists of all processes connected to a given
      coordinator. To have two simultaneous DMTCP computations on the
      same host, you will need two DMTCP coordinators listening to
      different port numbers. The command `dmtcp_coordinator` generates
      a new coordinator. By default, `dmtcp_launch` (`dmtcp_checkpoint`)
      will first look for an existing coordinator on the localhost on
      port 7779 and join that existing DMTCP computation. If no such
      coordinator is found, `dmtcp_launch` (`dmtcp_checkpoint`) will
      create a new coordinator and then join it as the first process of
      that computation. A checkpoint is initiated when the coordinator
      tells all its connected processes to create a checkpoint. Each
      client of the coordinator writes a file, `ckpt_*.dmtcp`, on its
      local machine, and the coordinator writes
      `dmtcp_restart_script.sh` in its own local directory. The script
      can be used to restart all processes using the `ckpt_*.dmtcp`
      files on the various hosts. Since the coordinator initiates all
      checkpoints, it is the coordinator that remembers the checkpoint
      interval. Both `dmtcp_command --interval` and
      `dmtcp_launch --interval` can be used to set the checkpoint
      interval on the coordinator.

  2.  ::: faq
      [Can I migrate my applications (restart on another host, possibly
      with a different Linux); and what if I see a message
      `illegal instruction`?]{#migrate}
      :::

      Yes, migration works. Look at dmtcp_restart_script.sh for some
      options on migrating both single-process and distributed process
      computations. Homogeneous host architectures are best, but some
      heterogeneity is also tolerated. This works best if the source and
      destination Linux distro are both recent. However, test the
      migration first. Problems are most likely to occur when migrating
      from a newer Linux/CPU to an older Linux/CPU, since an older
      distro is often not future-proof.

      Note that in migrating between arbitrary computers, it is possible
      to encounter \"**`illegal instruction`**\" on restart. This can
      occur if the CPUs of the source machine and destination machine
      are different. Most often, this occurs when migrating from a newer
      CPU to an older CPU that does not support the full range of
      extensions to the CPU instruction set. It may sometimes occur in
      migrating between AMD and Intel CPUs if the application or
      libraries were optimized during compilation for one CPU only. In
      principle, one can get around this with `gcc -mtune=generic`, but
      you would also have to make sure that (i) DMTCP, (ii) your target
      application, and (iii) *all libraries* used by it (including
      libc.so) are compiled with `gcc -mtune=generic`.\
          Finally, DMTCP generally supports process migration when
      migrating from an older Linux kernel to a newer Linux kernel. This
      works, because the checkpoint image of the target application
      contains all of the original run-time libraries, including
      libc.so. So, when an older libc.so makes a call to a newer Linux
      kernel, the newer Linux kernel will generally preserve backwards
      compatibility.

  3.  ::: faq
      [How can my software invoke a checkpoint or restart directly under
      control of my program?]{#dmtcpaware}
      :::

      The most full-featured mechanism is through [DMTCP
      plugins](FAQ.html#plugins). See especially [application-initiated
      checkpointing](http://github.com/dmtcp/dmtcp/tree/master/test/plugin/applic-initiated-ckpt)
      (using `dmtcp_checkpoint()`), and [application-delayed
      checkpointing](http://github.com/dmtcp/dmtcp/tree/master/test/plugin/applic-delayed-ckpt)
      (using `dmtcp_disable_ckpt()`/`dmtcp_enable_ckpt()`).

  4.  ::: faq
      [What is the exit code (return status) for a target application
      running under DMTP?]{#exitcode}
      :::

      Normally, commands like `dmtcp_launch a.out`
      (`dmtcp_checkpoint a.out`) and `dmtcp_restart ckpt_a.out_*.dmtcp`
      pass on the the exit code that is returned by a.out itself. If
      dmtcp_launch or dmtcp_restart is passed an invalid command line
      (e.g., no such ckpt file), then they will exit with exit code 99
      (by default), or the integer value of DMTCP_FAIL_RC if that
      environment variable has been set.

  5.  ::: faq
      [On restart, a process sees only the environment variables from
      the time of checkpoint (since DMTCP restores the previous memory).
      What do I do if I want to see the newest environment values at the
      time of restart?]{#modifyEnv}
      :::

      Please look at the directory of the [modify-env
      plugin](https://github.com/dmtcp/dmtcp/tree/master/plugin/modify-env).
      In particular, look at the `README` file and the `dmtcp_env.txt`
      example from that directory. You can invoke this plugin with:\
      `    dmtcp_launch --with-plugin `*`/absolute/path/to/`*`libdmtcp-modify-env.so`\
      (If you use `LD_LIBRARY_PATH`, you can also avoid the need for
      absolute pathnames.)

  6.  ::: faq
      [Does DMTCP support third-party plugins (add-ons) to change the
      behavior of DMTCP at run-time?]{#plugins}
      :::

      Yes. Please look at the [directory of DMTCP plugin
      examples](http://github.com/dmtcp/dmtcp/tree/master/test/plugin)
      for a flexible mechanism for third-party plugins (add-ons). This
      includes support for: (i) wrappers around system calls; (ii) hooks
      for particular events (e.g.: startup, ckpt, resume, restart); and
      (iii) for populating and querying a nameservice database across
      distributed processes. Application-initiated checkpointing is also
      provided. No re-compilation or relinking of the application
      software is necessary. The DMTCP source also provides a tutorial,
      [doc/plugin-tutorial.pdf](http://github.com/dmtcp/dmtcp/blob/master/doc/plugin-tutorial.pdf).

  7.  ::: faq
      [What if my target application runs as root, uses the setuid bit,
      uses capabilities, or uses other special privileges?]{#root}
      :::

      DMTCP works internally by preloading its own library into the
      target application (see [How does DMTCP
      Work?](FAQ.html#internalWorking)). Linux will not honor the setuid
      bit if a foreign library is being preloaded (for obvious reasons).
      So, either the application must be run in a mode not requiring
      special privileges, or DMTCP must be run in a privileged manner.
      This [\"Stack Overflow\" web
      page](http://stackoverflow.com/questions/18058426/does-using-linux-capabilities-disables-ld-preload)
      describes two strategies for allowing DMTCP to initially run with
      privileges. The constructor to use in the case of DMTCP is
      `dmtcp::DmtcpWorker::DmtcpWorker()` (or
      `dmtcp::DmtcpWorker::DmtcpWorker(bool)` for earlier than
      DMTCP-2.4) in `DMTCP_ROOT/src/dmtcpworker.cpp`. (If you\'re
      putting this in a gdbinit script, don\'t forget to use:
      `set break pending on` .) Group permissions, and security
      authorizations such as polkit, ACL and PAM may offer other
      options.

  8.  ::: faq
      [How can I read a summary of the contents of a DMTCP checkpoint
      image?]{#readdmtcp}
      :::

      Use readdmtcp.sh. (The example below assumes only one dmtcp ckpt
      file is present.)\
      `   `*`<DMTCP_DIR>`*`/util/readdmtcp.sh ckpt_*.dmtcp`\

  9.  ::: faq
      [How do I debug my application under GDB when I am using
      DMTCP?]{#debugging}
      :::

      Detailed advice is available in the file
      [doc/debugging-dmtcp.txt](http://github.com/dmtcp/dmtcp/blob/master/doc/debugging-dmtcp.txt)
      (although this FAQ is often more current). General advice
      follows.\

      When using GDB with DMTCP, you may find it useful to load some
      utilities (available since DMTCP-2.6.1 and DMTCP-3.0):\
      ` (gdb) source util/gdb-dmtcp-utils`\
      `(gdb) dmtcp # lists the new GDB commands`\

      For compiling DMTCP with debugging support under GNU gcc, we
      recommend:\
         `./configure --enable-debug` (\"-Wall -g3 -O0\" for gcc and
      g++)\
         `make -j clean && make -j`\
      (Omit the \"`-j`\" if you are on a less powerful computer.)

      *CATCHING DMTCP INTERNAL ERRORS (CREATE A CORE DUMP):*\
      Prior to running `dmtcp_launch`, do:\
      ` ulimit -c unlimited && export DMTCP_ABORT_ON_FAILED_ASSERT=1 `\
      (and also, if using GDB, set a breakpoint at `_exit`)

      *DEBUGGING DURING INITIAL LAUNCH:*     Run it as:
      `gdb --args dmtcp_launch ./a.out`\
      (Older versions of DMTCP use `dmtcp_checkpoint` instead of
      `dmtcp_launch`.)\
      Then `dmtcp_launch` will call execvp on `./a.out`. So, try the
      following:\
      ` (gdb) break execvp`\
      `(gdb) run`\
      `(gdb) # [stops at execvp]`\
      `(gdb) break main`\
      `(gdb) next`\
      `(gdb) next`\
      `(gdb) ...`\
          Note that `dmtcp_launch` calls execvp to execute the main
      routine of the application (`a.out` in the above example). If you
      want to see the actions of the dmtcphijack.so library starting
      after the call to execvp and before the application\'s main
      routine, then at the beginning of your GDB session, do:\
      ` (gdb) break execvp`\
      `(gdb) run`\
      `(gdb) # 'pending on' is required if using a gdbinit script`\
      `(gdb) set breakpoint pending on`\
      `(gdb) # For DMTCP-2.4 and later in DMTCP-2.x:`\
      `(gdb) break dmtcp_initialize`\
      `(gdb) # For DMTCP-3.0 and later:`\
      `(gdb) #   break dmtcp_initialize_entry_point`\
      `(gdb) #     OBSOLETE: For prior to DMTCP-2.4:`\
      `(gdb) #     OBSOLETE: break 'dmtcp::DmtcpWorker::DmtcpWorker(bool)'`\
      `(gdb) continue # Might need to repeat 'continue' a few times.`\
      We have found the GDB command `info proc mappings` useful for
      deciding if an address belongs to libc.so, dmtcphijack.so, your
      target application, or other.\

      *NOTE:* If you want to trace the internals of DMTCP (in addition
      to using GDB as above), see [*tracing DMTCP
      internals*](FAQ.html#jassert).\

      *DEBUGGING DURING CHECKPOINT:* Begin your DMTCP session under GDB
      (`gdb --args dmtcp_launch ...`), and just `run` (without any
      checkpoints). At the time of checkpoint, the checkpoint thread
      (typically thread 2 in GDB) will send a SIGUSR2 to each user
      thread. By default, GDB will intercept that signal, announce it to
      the user, and wait until the user executes:\
      ` (gdb) signal SIGUSR2`\
      At this time, you can gain control with GDB. Tell GDB to switch to
      `thread 2`, and you can then examine the stack and set a
      breakpoint, before issuing the \"`signal SIGUSR2`\" command.

      *DEBUGGING DURING RESTART:*     To capture your process under GDB
      during `dmtcp_restart`, you need a more roundabout strategy. This
      is because `dmtcp_restart` calls `mmap` to reload the memory of
      your process. So, the best way is to use `gdb attach` or
      `` gdb ./a.out `pgrep -n a.out` `` after your process has
      restarted.\
          In order to assist in using gdb to attach, your restarted
      process can be forced to pause deep within DMTCP just as it
      restarts, by setting the environment variable
      `DMTCP_RESTART_PAUSE2`. (Set `DMTCP_RESTART_PAUSE2` *before* the
      original `dmtcp_launch`, since the restarted process will remember
      only the original environment variables prior to checkpoint.
      *(Prior to DMTCP-2.4, the variable had the name
      MTCP_RESTART_PAUSE.)* The environment variable
      `DMTCP_RESTART_PAUSE` is available to capture the restart even
      earlier \-\-- primarily of interest for DMTCP developers.     On
      restart, dmtcp_restart will then pause with a message to attach
      using a gdb command. In earlier versions of DMTCP, the gdb attach
      command may fail with: `Operation not permitted`. In those cases,
      you may execute: `echo 0 > /proc/sys/kernel/yama/ptrace_scope`
      (requires root privilege, and may pose a security risk).\
          Beginning with DMTCP-2.4, one can also set the environment
      variable `DMTCP_GDB_ATTACH_ON_RESTART` prior to executing
      `dmtcp_restart`. This also allows one to use \"gdb attach\" on the
      restarted process for debugging.\
          Note that after DMTCP 2.0, the MTCP directory was merged into
      DMTCP itself, and it is no longer possible to run MTCP as a
      standalone application. If you need that functionality, please
      consider using `dmtcp_launch --no-coordinator` with the latest
      DMTCP release. Having said that, if you are using an older version
      of DMTCP, The information above is valid.

      *DEBUGGING PLUGINS:* Some bugs may be produced by interactions
      among plugins. In such cases, consider temporarily disabling
      plugins, and see if the bug goes away. (This is similar to the
      standard advice often given for web browsers.) In some exceptional
      cases, there can also be a bug in the interaction with internal
      plugins of DMTCP. See [\"debugging internal DMTCP
      plugins\"](FAQ.html#debugPlugins) for more information concerning
      this issue.

      In debugging during restart using \'gdb attach\', we have reports
      in early 2020 saying that under Ubuntu, we are not seeing the
      symbol tables when we attach. This problem is seen *only* on
      Ubuntu (e.g., Ubuntu 18.04). A stack is seen with the addresses,
      but without the function names. We see this on Ubuntu, but *not*
      on CentOS. We are guessing that GDB under Ubuntu is having trouble
      \"walking the stack\" to find the symbol table. As a workaround,
      after restart, please use inside GDB:\
      `(gdb) source DMTCP_ROOT/util/gdb-add-symbol-files-all` (or the
      older bash shell script from the command line,
      `DMTCP_ROOT/util/gdb-add-symbol-file` , if not using the latest
      DMTCP). The shell script
      `DMTCP_ROOT/util/save-symbol-files-to-gdb-script.py` may also be
      useful in this setting.

  ::: faqHeader
  [Architectures Supported by DMTCP]{#architectures}
  :::

  1.  ::: faq
      [What CPUs has DMTCP been ported to?]{#cpuPorts}
      :::

      DMTCP supported x86 and x86_64 since the beginning. It has been
      ported to the 32-bit ARM CPU (armv7/armv7a), using the newer EABI
      API for Linux on ARM. An experimental port to 64-bit ARM (armv8)
      has been added as of DMTCP-2.4.0. For porting to other CPUs,
      please see
      [src/mtcp/PORTING](http://github.com/dmtcp/dmtcp/blob/master/src/mtcp/PORTING)
      (notes on how to port DMTCP).

      DMTCP has also been verified to work on the Intel Xeon Phi (back
      end, only, at this time) when built with the Intel icc compiler.
      We used\
      `./configure --host=mic CC=icc CXX=icpc CFLAGS=-mmic CXXFLAGS=-mmic LDFLAGS=-mmic`\
      to build on the Intel MIC. Optionally, one can also add
      \"`-static-intel`\" to CFLAGS, CXXFLAGS and LDFLAGS.

  2.  ::: faq
      [How can I compile DMTCP for mixed x86/x86_64 architectures
      (multi-arch/multilib for mixed 32-/64-bit)?]{#intel32-64}
      :::

      See
      [doc/multi-arch.txt](http://github.com/dmtcp/dmtcp/blob/master/doc/multi-arch.txt)
      for details. In short,\
      `./configure --enable-m32 && make clean && make -j && make install`\
      `./configure && make clean && make -j && make install`\
      Use `./configure --prefix=$PWD/build` if you wish to build a local
      copy in \$PWD/build, instead of installing globally.

      Note that `--enable-m32` will not create the necessary DMTCP
      commands on a 64-bit Linux. So, *on a 64-bit Linux*, you will
      still need the 64-bit install, even if you intend only to run with
      32-bit targets.

      On recent versions of DMTCP (late 2019), a \--enable-multilib
      option has been made available to automate this.

  3.  ::: faq
      [What operating systems has DMTCP been ported to?]{#osPorts}
      :::

      DMTCP operates only under Linux as of this writing. Because its
      design stays close to the POSIX API, it can be ported to other
      operating systems, given sufficient demand. If someone is
      interested in doing the work, please write to us, and we will
      share our ideas on how to do that port.

      See also [\"Implementing Checkpointing for
      Android\"](http://www.slideshare.net/jserv/implement-checkpointing-for-android-elce2012)
      for work toward porting DMTCP to Android.

  4.  ::: faq
      [What types of networks does DMTCP support?]{#networkPorts}
      :::

      DMTCP works directly with both TCP and InfiniBand. It would also
      be relatively easy to port it to IP, but we haven\'t seen a demand
      for this. When using InfiniBand, launch with:
      `dmtcp_launch --infiniband ...`

  5.  ::: faq
      [What Linux distributions do you test on?]{#distros}
      :::

      There are also \"dmtcp\" packages in Debian (since version 7.0,
      \"wheezy\"), Ubuntu (since version 11.10), Fedora (since
      version 17), and Red Hat (via [Fedora
      EPEL](https://fedoraproject.org/wiki/EPEL)). In-house, we commonly
      use DMTCP under Ubuntu, CentOS, and openSUSE. On an irregular
      basis, we also test on other distributions.

  ::: faqHeader
  [Performance]{#performance}
  :::

  1.  ::: faq
      [My application takes several seconds (or longer) to checkpoint
      and restart. What can I do to speed it up?]{#speed}
      :::

      Small applications should checkpoint and restart in a second.
      There are several ways to speed up checkpoint/restart for larger
      applications:
      a.  The disk is usually the slowest part of checkpoint/restart.
          Consider using a RamDisk. For example:\
          ` sudo mount -t ramfs -o size=200m ramfs `*`/path/to/dmtcp_ckpt_dir`*\
          `export DMTCP_CHECKPOINT_DIR=`*`/path/to/dmtcp_ckpt_dir`*\
          `rm -f `*`/path/to/dmtcp_ckpt_dir/ckpt_*.dmtcp`*\
          `dmtcp_launch `*`YOUR_APP`*\
          `dmtcp_restart `*`/path/to/dmtcp_ckpt_dir/ckpt_*.dmtcp`*\
          *(Warning: ramfs can continue to grow with the total size of
          files in the dmtcp_ckpt_dir, eventually freezing your system
          if you write too much. The related tmpfs does not suffer from
          this, but it uses the swapfile on disk, which can slow it down
          for large writes.)*
      b.  Restart will be faster with the environment variable
          DMTCP_TMPDIR (on ckpt and restart) pointing into the RamDisk
          created above.\
          *(Set DMTCP_TMPDIR before the initial launch of your
          application, since the environment variable is saved with your
          checkpoint image. This policy may be changed in the future.)*
      c.  By default, DMTCP uses gzip for dynamic compression of
          checkpoint images. Consider using `dmtcp_launch --no-gzip` .
          Alternatively, set an environment variable:
          `export DMTCP_GZIP="0"` . On restart, DMTCP will auto-detect
          whether gzip was used.
      d.  Gzip was chosen because it is available almost universally.
          Some examples of newer, faster compression packages are:
          [Snappy](http://code.google.com/p/snappy/),
          [LZO](http://www.oberhumer.com/opensource/lzo/),
          [FastLZ](http://fastlz.org/), and
          [QuickLZ](http://www.quicklz.com/). Currently, you will have
          to modify the DMTCP source code to use these. With enough
          demand, we will make it easy for the end user to select a
          different compression package.
      e.  Two configure options for improving checkpoint and restart
          speeds are offered. Please test that these optimizations are
          compatible with your application.\
          - `./configure --enable-forked-checkpointing` : Use fork-based
            copy-on-write to have a child checkpoint while the parent
            continues to execute
          - `./configure --enable-fast-restart` : mmap-based on-demand
            paging from the checkpoint image

  2.  ::: faq
      [Can I tell DMTCP that some of my memory does not need to be
      checkpointed (specifying *cutouts*, for a smaller checkpoint
      image)?]{#size}
      :::

      If you write all zeroes to the memory region that does not need to
      be checkpointed, then DMTCP will convert those pages into
      zero-fill-on-demand pages in the checkpoint image. This creates a
      smaller checkpoint image, and results in a faster restart.

  ::: faqHeader
  [Internals:]{#internals}
  :::

  1.  ::: faq
      [How does DMTCP work?]{#internalWorking}
      :::

      A DMTCP coordinator process is created on a host (default:
      localhost). As new processes are created (via fork or ssh), the
      LD_PRELOAD environment variable (supported by the Linux loader) is
      used to preload the DMTCP library (dmtcphijack.so). That library
      runs before the routine main(). It creates a second thread (DMTCP
      checkpoint thread). The checkpoint thread then creates a socket to
      the DMTCP coordinator and registers itself. The checkpoint thread
      also creates a signal handler (SIGUSR2 by default). Control is
      then returned to the original user thread, which executes its
      standard startup routines. The DMTCP coordinator can request a
      checkpoint by sending a message through the socket to the
      checkpoint thread. The checkpoint thread then sends the checkpoint
      signal (SIGUSR2) to each of the user threads. (Note that the
      checkpoint signal is for internal DMTCP use only. It should not be
      used by non-DMTCP programs.)\
          Note that it is shown how to see a summary of the [contents of
      a DMTCP checkpoint image](FAQ.html#readdmtcp) in a previous
      question.

  2.  ::: faq
      [Is there documentation on the internals of
      DMTCP?]{#documentation}
      :::

      Some sources of information follow. If you wish to cite DMTCP,
      please cite the [paper by Ansel et al.](publications.html)
      i.  The best high-level overview of the design of DMTCP is still
          in the paper [DMTCP: Transparent Checkpointing for Cluster
          Computations and the Desktop](publications.html), by Ansel
          et al. (2009).
      ii. For the design of just the single-process checkpointing layer
          (MTCP), see [Transparent User-Level Checkpointing for the
          Native POSIX Thread Library for Linux](publications.html), by
          Rieker et al. (2006).
      iii. For a recent overview of the DMTCP architecture, see
           [doc/architecture-of-dmtcp.pdf](http://github.com/dmtcp/dmtcp/tree/master/doc/architecture-of-dmtcp.pdf)
           (available with the source distribution).
      iv. For low-level documentation of the implementation of DMTCP,
          see the [doc](http://github.com/dmtcp/dmtcp/tree/master/doc/)
          subdirectory of the source distribution.

  3.  ::: faq
      [Can I enable tracing of DMTCP internals?]{#jassert}
      :::

      Yes. You will have to re-configure and re-make:\
      `./configure --enable-logging && make -j5 clean && make -j5`\
      After this, you will see lots of output sent to stderr on screen.
      In addition, there will be files in
      `$DMTCP_TMPDIR/dmtcp-$USER@$HOST` (where `$DMTCP_TMPDIR` is
      `$TMPDIR` or `/tmp`). Look at the files `jassert_*.log` in the
      given directory. To add low-level debugging (MTCP for single
      processes), change `mtcp/Makefile` to uncomment:\
      `CFLAGS += -O0 -g -DDEBUG -DTIMING -Wall`\
      *NOTE:* If you also want to debug under GDB, see [*debugging under
      GDB*](FAQ.html#debugging).

  4.  ::: faq
      [I suspect a bug concerning an interaction with an internal plugin
      of DMTCP. How can I debug this?]{#debugPlugins}
      :::

      Normally this should not happen. However, a complex new user
      plugin might uncover a bug in DMTCP itself. If so, the first thing
      to look at is a bug in the interaction with an internal DMTCP
      plugin. Just as browser plugins have a \"safe mode\", DMTCP can be
      loaded without some of its internal plugins.\
           If one is only testing the initial launch (no checkpoint or
      restart, one can safely disable all plugins for \"save mode\".
      However, if testing checkpoint or restart, then some (but not all)
      of the plugins will generally be required for correct operation.\
           All plugins can be disabled by launching an application with
      `dmtcp_launch --disable-all-plugins` . If one wishes to disable
      only some of the plugins, then one must modify the source code.
      The file `src/dmtcp_launch.cpp` has global variables of the form
      `enableIPCPlugin=true`, etc. Try setting some of the internal
      plugins to false, re-compiling, and testing if the bug goes away.
      If an interaction with an internal plugin is uncovered, try
      commenting out some of the wrapper functions in that plugin. Note
      that it is generally safe to disable the internal plugins when
      testing only DMTCP launch and resume after writing a checkpoint.
      However, in testing DMTCP restart (from a checkpoint image file),
      some of of the DMTCP internal plugins may be required for correct
      operation.

  5.  ::: faq
      [What is the run-time overhead of DMTCP?]{#internalOverhead}
      :::

      The run-time overhead of DMTCP is usually negligible. When there
      is no checkpoint or restart in process, DMTCP code will run only
      within DMTCP wrappers around certain less frequently used system
      calls. Examples of such wrappers are wrappers for open(),
      getpid(), socketpair(), etc. We explicitly do *not* place a
      wrapper around read() or write(), since those are frequently
      called system calls that could produce measurable run-time
      overhead.

  6.  ::: faq
      [What O/S features are supported by DMTCP?]{#osFeatures}
      :::

      Among the Linux features supported by DMTCP are open file
      descriptors, pipes, sockets, signal handlers, process id and
      thread id virtualization (ensure old pids and tids continue to
      work upon restart), fifos, process group ids, session ids, ptys,
      terminal attributes, System V shared memory (shmget, etc.),
      timers, epoll, eventfd, signalfd, and mmap/mprotect (including
      mmap-based shared memory). Such common O/S daemons as NSCD and
      LDAP are also transparently supported.

  ::: faqHeader
  [About the DMTCP Project]{#dmtcpProject}
  :::

  1.  ::: faq
      [Who should I write to for support?]{#supportContact}
      :::

      Please see the [\"Contact Us\" links](contactUs.html) for writing
      to us. That link includes pointers to the public DMTCP forum, and
      a private e-mail for private comments. Other possibilities are to
      add a bug report to [the bug
      tracker](http://sourceforge.net/tracker/?group_id=194616&atid=950143),
      or to write to an individual
      [administrator](http://sourceforge.net/project/memberlist.php?group_id=194616).
      We are also always interested in finding others interested in
      helping develop DMTCP as an open source project.

  2.  ::: faq
      [When was work on DMTCP begun, and who works on it now?]{#history}
      :::

      The origins of DMTCP lie in a project begun in Fall, 2004, and
      reported on at the CCGrid-06 conference (*Transparent Adaptive
      Library-Based Checkpointing for Master-Worker Style Parallelism*).
      Since then, The work has added more ambitious goals. The list of
      active developers continues to change over time. As of this
      writing, the sourceforge site lists ten developers/administrators.
      We are always happy to include new developers.

  3.  ::: faq
      [How should I cite DMTCP in a publication?]{#citeDMTCP}
      :::

      Please see the [Publications page](publications.html) for the
      standard citation at the top of that page.

------------------------------------------------------------------------

------------------------------------------------------------------------

\

::: faqHeader
[]{#targetApps} **II. Support for Specific Types of Software
Applications**
:::

::: faqHeader
[What Applications does DMTCP Support?]{#supportedApps}
:::

1.  ::: faq
    [Is there a simple, general description of what applications are
    supported?]{#generalSupport}
    :::

    Yes. See [this page for a general discussion](supportedApps.html).
    In addition, note the availability of [DMTCP plugins
    (add-ons)](http://github.com/dmtcp/dmtcp/tree/master/test/plugin/)
    that allow end users to easily extend the features of DMTCP.

2.  ::: faq
    [Does DMTCP support multi-threaded and distributed
    programs?]{#distributed}
    :::

    Yes. For programs that spawn processes on remote hosts, DMTCP
    currently assumes that this is done internally using ssh to a
    \"known host\", and so no password will be required. This is the
    case, for example, for most TCP/IP-based MPI programs. To restart on
    different hosts, edit the \'ssh\' lines in
    `dmtcp_restart_script.sh` . See below for [further discussion on
    MPI](FAQ.html#mpi). See
    [QUICK-START.md](http://github.com/dmtcp/dmtcp/tree/master/QUICK-START.md)
    for additional details.

3.  ::: faq
    [Does DMTCP support Java?]{#javaSupport}
    :::

    Yes. Starting with release 1.2.4, DMTCP supports Java. If you are
    using Oracle Java (formerly Sun Java), you may wish to use the flag
    `java -Xmx512M` to limit memory size for a faster checkpoint. This
    is not needed for OpenJDK Java.

4.  ::: faq
    [Does DMTCP support checkpointing of Matlab?]{#matlabSupport}
    :::

    Yes. Please [see below](FAQ.html#matlab).

5.  ::: faq
    [Does DMTCP support checkpointing of]{#RCkpt} [R
    programs](http://www.r-project.org/) (for statistical computing)?
    :::

    Yes. It passes our internal tests, but we would appreciate having a
    more intensive user of R provide feedback to us.

6.  ::: faq
    [Does DMTCP support MPI?]{#mpiSupport}
    :::

    Yes. See the [section below on MPI](FAQ.html#mpi).

7.  ::: faq
    [Does DMTCP support multi-threaded languages such as OpenMP and
    Cilk?]{#openmpSupport}
    :::

    Yes. DMTCP had partial support for OpenMP in the past. Starting with
    release 1.2.4, DMTCP fully supports OpenMP and Cilk.

8.  ::: faq
    [Does DMTCP support integration with batch queues (resource
    managers)?]{#batchQueue}
    :::

    As of DMTCP version 2.4, DMTCP supports SLURM and Torque. See below
    for [additional details](FAQ.html#batchQueuePorts).

9.  ::: faq
    [Does DMTCP support integration with Condor?]{#condor}
    :::

    Yes. See the web page on [Condor
    integration](http://dmtcp.sourceforge.net/condor.html).

10. ::: faq
    [Does DMTCP support]{#screenSupport} [GNU
    screen](http://www.gnu.org/software/screen/) sessions?
    :::

    Yes. Starting with release 1.2.0, DMTCP supports GNU screen.

11. ::: faq
    [Can DMTCP checkpoint a GDB session?]{#gdb}
    :::

    This is still considered experimental, but it should be reasonably
    stable in DMTCP version 1.2.4 and the upcoming DMTCP version 1.3.0.
    Try: `configure --enable-ptrace-support` to use this feature.

12. ::: faq
    [Does DMTCP support X-Windows graphics (GUI)
    programs?]{#xwindowsSupport}
    :::

    Partially. DMTCP supports X-Windows programs with the help of VNC.
    Recall that *vncserver* will create a virtual desktop in which you
    can run your graphics application, and *vncviewer* invokes an
    Xserver to display the graphics. So, the recipe is:\
    `dmtcp_launch vncserver :1`\
    `vncviewer localhost:1`\
    `my-X-windows-app`\
    To checkpoint, kill the vncviewer and then do:\
    ` dmtcp_command --checkpoint`\
    `vncviewer localhost:1 # to re-connect the graphics`\
    Later, to restart from a checkpoint, do:\
    ` ./dmtcp_restart_script.sh`\
    `vncviewer localhost:1 # to re-connect the graphics`\
    Note that VNC does not support such X-Windows extensions as 3D
    graphics (3D visualization such as in many scientific graphics
    simulations) nor video nor sound. We are continuing to look at
    improving graphics support.

\

------------------------------------------------------------------------

::: faqHeader
[Matlab:]{#matlab}
:::

1.  ::: faq
    [Does DMTCP support checkpointing of Matlab programs?]{#matlabCkpt}
    :::

    Yes. But Matlab is a moving target, as it continues to use newer
    features of Linux. It is best to use a recent DMTCP. DMTCP-2.4 added
    support for matlab-2013 and later. DMTCP-2.3.x supported Matlab
    through matlab-2012. Much earlier, DMTCP-1.2.5 had added an
    enhancement for the case when Matlab is in the middle of talking to
    its license server at checkpoint time.

\

------------------------------------------------------------------------

::: faqHeader
[MPI:]{#mpi}
:::

1.  ::: faq
    [Does DMTCP support checkpointing of MPI programs?]{#mpiCkpt}
    :::

    Yes. And to restart on different hosts, edit the \'ssh\' lines in
    `dmtcp_restart_script.sh` . DMTCP operates by checkpointing the
    sockets (or InfiniBand connections, if using `--infiniband`) created
    by the MPI library. Hence, it is transparent to MPI and doesn\'t
    require any particular MPI configuration or hooks. In principle,
    DMTCP should run on any MPI over TCP/IP. We usually test on
    [Open MPI](http://www.open-mpi.org/),
    [MVAPICH-2](http://mvapich.cse.ohio-state.edu/) and
    [MPICH-2](http://www.mcs.anl.gov/research/projects/mpich2/). If you
    find an MPI that we don\'t support, *this is a bug in DMTCP*. We
    would be appreciative if you can file a bug report. For further
    details on using MPI, see
    [QUICK-START.md](http://github.com/dmtcp/dmtcp/tree/master/QUICK-START.md).
    - As of DMTCP-2.4, DMTCP should offer robust support for popular
      implementations of MPI, along with support for the SLURM batch
      queue. (See the [example SLURM scripts for using
      DMTCP](https://github.com/dmtcp/dmtcp/tree/master/plugin/batch-queue/job_examples).)

2.  ::: faq
    [Does DMTCP support MPI for InfiniBand, Myrinet, or
    iWARP?]{#mpiInfiniBand}
    :::

    DMTCP supports the OFED implementation of InfiniBand (librdmacm and
    libibverbs API). These libraries support InfiniBand and iWARP. At
    this time, we have not seen sufficient demand to add support for
    other APIs like uDAPL, Mellanox verbs, or Myrinet API.

3.  ::: faq
    [What types of batch queues (resource managers) does DMTCP
    support?]{#batchQueuePorts}
    :::

    As of DMTCP version 2.4, DMTCP supports SLURM and Torque. The
    integration of SLURM with MPI has been especially intensively
    tested. Support for both is implemented as a plugin, and can be
    found in the
    [plugin/batch-queue](http://github.com/dmtcp/dmtcp/tree/master/plugin/batch-queue/)
    directory, which includes example submission scripts for SLURM/DMTCP
    and Torque/DMTCP. This is provided by Artem Polyakov, who can be
    reached as artpol84 through gmail. Ports to other batch queues can
    be added relatively easily using this model.

\

------------------------------------------------------------------------

Click [here for comments.](contactUs.html){.sidebar}

[![SourceForge.net
Logo](http://sourceforge.net/sflogo.php?group_id=96405&type=5){border="0"
height="62" width="210"}](http://sourceforge.net)
::::::::
