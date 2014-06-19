flock-visudo
============

Background:
 On Linux, there are two locking APIs: FLOCK and the POSIX lockf.
 Locking using one API appears to have no effect locks used with 
 the other API.

 sudo can be built to use either flock or lockf, but there is no
 way to select after compile time. There is a command
 line utility for flock but no comparable one for lockf. Therefore
 by default there is no fail-proof way to interact with the sudoers
 file both from scripts and visudo.  This script wraps the call to
 visudo in a call to flock such that locking can be performed between
 command line scripts and visudo.

