---
layout: post
title: Overcoming Hanging in SSH connections.
---


## The Story
Running, scheduling and resource allocation of computation heavy jobs in HPC clusters were made easy when WorkLoad managers such as SLURM, OpenHPC and other cluster software were introduced. But, that might not be the case every time.  Due to COVID-19 crisis, PARAMShivay ( Supercomputing centre at IIT(BHU) ) staff decided to shut down all its services. To serve the needs of critical projects, Institute allocated two compute nodes at CCIS ( Centre for Computing and Information Services, IIT(BHU) ). SLURM manages PARAMShivay cluster, but the newly allocated compute nodes were conventional Red-Hat VMs. My thesis project requires at least six continuous hours of model training. The problem is that there is something (usually a firewall or load-balancer), which is dropping idle SSH sessions. SSH connections generally freeze when they become idle for a while. This was when I came across the `nohup` command.
  
## Fire Up your terminals!
The command below executes the `python main.py` command in the background in such a way that the subsequent logout does not stop it.
nohupping backgrounded jobs is typically used to avoid terminating them when logging off from a remote SSH session. The output is written into `nohup.out` file which will be generated in the same directory.
  
```bash
# Remember adding & at the end
$ nohup python main.py &
# Take a coffee break
$ exit
```
  
## Technically Speaking
The name nohup stands for "no-hangup." The hangup (HUP) signal, which is usually sent to a process to inform it that the user has logged off (or "hung up"), is intercepted by nohup, allowing the process to continue running.
  
## Viewing nohup processes
```bash
$ ps xw
PID  TTY      STAT   TIME COMMAND
1031 tty1     Ss+    0:00 /sbin/getty -8 38400 tty1
10826 ?        Sl     0:18 python main.py
```
Here, TTY column tells us which terminal is associated with the process. TTY columns with `?` are running nohup processes.


## Footnotes
* [man nohup]


[man nohup]: http://man7.org/linux/man-pages/man1/nohup.1p.html

<!-- vim: set tw=90 sts=-1 sw=4 et spell wrap: -->