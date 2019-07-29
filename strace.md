# strace

```bash
# Basic stracing
strace <command>

# save the trace to a file
strace -o strace.out <other switches> <command>

# follow only the open() system call
strace -e trace=open <command>

# follow all the system calls which open a file
strace -e trace=file <command>

# follow all the system calls associated with process
# management
strace -e trace=process <command>

# follow child processes as they are created
strace -f <command>

# count time, calls and errors for each system call
strace -c <command>

# trace a running process (multiple PIDs can be specified)
strace -p <pid>
```

## Trace access to a file

```bash
strace -P /etc/os-release cat /etc/os-release > /dev/null
```


## trace family of syscalls

```bash
strace -e %%stat cat /etc/os-release > /dev/null
```

Classes:

- `%%stat`: `%stat` + `%lstat` + `fstat` + `statx`
- `%file`: syscalls that take a filename argument
- `%desc`: file descriptor syscalls
- `%net`: network related syscalls

