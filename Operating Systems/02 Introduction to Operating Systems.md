# 2.0 Introduction

**What does running a program mean?**

The processor **Fetches** an instruction from memory, **Decodes** the instruction (convert it into a way that CPU can understand), **Executes** the instruction. This is a simple [Von Neumann model of computing](https://www.geeksforgeeks.org/computer-organization-von-neumann-architecture/) 

***OS***
- Responsible for making it easy to run many programs at once
- Allows programs to use shared memory
- Enables programs to use I/O devices

The primary way OS does this is through *virtualization*. The OS takes the physical resources and then transforms them to easy to use virtual form. Thus we refer OS as <ins>Virtual Machine</ins>  sometimes. Since we can see that OS is allowing many programs to run at same time using virtualization, It is indeed managing the resources (sharing memory, CPU, disk) between programs. OS is sometimes referred to as <ins>Resource Manager</ins>

For the users to make use of OS (such as running a program, or allocating memory, or accessing a file), the OS provides some APIs that you can call. A typical OS exports a few hundreds **system calls** that are available for applications to use.

# 2.1 Virtualizing The CPU

```c
#include <stdio.h>
#include <stdlib.h>
#include "common.h"

int main(int argc, char *argv[])
{
    if (argc != 2) {
	fprintf(stderr, "usage: cpu <string>\n");
	exit(1);
    }
    char *str = argv[1];

    while (1) {
	printf("%s\n", str);
	Spin(1);
    }
    return 0;
}

```

The above program just prints the string that is given as input by user and waits for seconds and the prints again until user interrupts it (^c)