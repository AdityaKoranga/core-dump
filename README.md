# core-dump

```bash
ulimit -c unlimited
```
It allows the system to create core files of unlimited size. Core files are used for debugging and are generated when a program crashes. They contain a memory dump of the process at the time of the crash, which can be analyzed to determine the cause of the crash.
Setting the core file size to unlimited is useful when debugging programs and you want to ensure that the core file is not truncated due to size limitations.

```bash
echo 1 > /proc/sys/kernel/core_uses_pid
```

By echoing 1 into this file, you enable the behavior where the PID of the process is appended to the name of the core file. For example, if a process with PID 1234 crashes, the core file might be named core.1234.
This is useful for distinguishing between core files from different processes, especially when multiple processes might be crashing and generating core files in the same directory.
