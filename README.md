# [DMTCP: Distributed MultiThreaded CheckPointing](http://dmtcp.github.io/) 
[![Build](https://github.com/dmtcp/dmtcp/actions/workflows/make-check.yml/badge.svg)](https://github.com/dmtcp/dmtcp/actions/workflows/make-check.yml)

DMTCP is a tool to transparently checkpoint the state of multiple simultaneous
applications, including multi-threaded and distributed applications. It
operates directly on the user binary executable, without any Linux kernel
modules or other kernel modifications.