IMPLEMENTATION
==============

Eclipse:
* "Type 'bool' could not be resolved" - Index -> Freshen All Files

Remote debug:
* gdb server (program is running) + Eclipse debug (debugger w/ code)
* cd ~/p/hstr/github/hstr/Debug && gdbserver :9999 ./hh
* Eclipse/Debug Configuration/Using GDB Manual Remote Debugger launching|Debugger tab/Connection port: 9999 
