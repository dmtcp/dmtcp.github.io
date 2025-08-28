---
title: Plugins
layout: home
nav_order: 8
---

## DMTCP Plugin Interface:

DMTCP plugins provide a flexible model with which to write an add-on
library that can: support DMTCP event hooks; add custom wrappers around
system calls; and add a custom distributed name-service facility through
the DMTCP coordinator. Some DMTCP plugin examples can be found in the
[*test/plugin*](https://github.com/dmtcp/dmtcp/tree/master/test/plugin)
directory of the source distribution.

The DMTCP source also provides a plugin tutorial,
[doc/plugin-tutorial.pdf](https://github.com/dmtcp/dmtcp/blob/master/doc/plugin-tutorial.pdf).

## Quick start to learning DMTCP plugins:

                
                    cd DMTCP_ROOT/test/plugin
                    cd sleep1
                    make clean
                    make -n check # To see how to compile and run it.
                    make check    # To actually compile and run it.
                    # Kill the running process using ^C, and then restart it:
                    ./dmtcp_restart_script.sh  

After that, read the source code. It should be small and easy to read.
For more complex examples, read
[*DMTCP_ROOT/test/plugin/README*](https://github.com/dmtcp/dmtcp/blob/master/test/plugin/README)
and try some examples in the various subdirectories of
*DMTCP_ROOT/test/plugin* .

## Python Interface:

DMTCP also provides a simple Python module for accessing DMTCP functions
within a Python session. You can import the Python module found as
[*contrib/python/dmtcp.py*](https://github.com/dmtcp/dmtcp/blob/master/contrib/python/dmtcp.py).
Other Python utilities are also in
[*contrib/python/*](https://github.com/dmtcp/dmtcp/tree/master/contrib/python).

------------------------------------------------------------------------

Click [here for comments.](contactUs.html){.sidebar}

[![SourceForge.net
Logo](http://sourceforge.net/sflogo.php?group_id=96405&type=5){border="0"
height="62" width="210"}](http://sourceforge.net)
