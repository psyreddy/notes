# 4. The Abstraction: The Process 

[Reference](https://pages.cs.wisc.edu/~remzi/OSTEP/cpu-intro.pdf)

> A process is a *running program*

The program is a lifeless things that will be residing on the disk. The OS takes the program and puts it into action (converts to a process). It turns out that in general a user wishes to run many programs at once (for instance me while writing this notes have kept vscode, pdf reader, music player open at same time). Not only these system will be running typically tens or hundreds of programs at the same time.

The OS creates this illusion by virtualizing the CPU. The OS runs one process, then pause it, runs other and so on. Doing this the OS creates an illusion on infinate CPUs. This technique is called **time sharing** of CPU. The main cost of this method is performance. If we run many processes at once, it may affect the performance of each process.

For implementing the virtualization, OS requires some low level mechanisms and high level intelligence.