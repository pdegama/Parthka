+++
date = '2025-10-04T17:49:42+05:30'
draft = false
title = 'Work behind System call!'
description = "Why we need of System call during File System, I/O, Socket, polling, etc... operations?"
cover = "/img/system_call.png"
+++

# Understanding System Calls

We are developers, and we use computers daily. We do programming on computers and write our code in different languages like Go, Zig, JavaScript, Node.js, etc.

We also write code for file handling like open, read, write, and unlink files. We use socket programming for Network I/O, and `fork()` to create new child processes, `sleep()`, etc. — all of these are **System Calls**.

> A System Call is an interface — a programming interface used to request resources and services.

Nowadays, we have high-level programming languages like Go, JavaScript (with runtimes like Bun, Node.js), Python, Java, etc. These languages use system calls behind the scenes.  
Low-level programming languages like C and C++ have direct wrappers around system calls such as `read()`, `accept()`, `unlink()`, etc.

---

## How it works

Most Operating Systems have 2 modes: **Kernel mode** and **User mode**.  
Kernel mode has full privileges, while user mode has limited privileges. We use user mode for daily work — we don’t have permission to directly access hardware; our access is limited. The kernel, however, has full control of the hardware.

When we need to access hardware, we call the kernel using the **System Call** interface. The kernel then checks whether the user is authorized, has permission, and whether resources are available. After passing all safety checks, it grants permission to access the requested resources or hardware.

```goat
             +-------------+     +--------+                                        +------------------------+
User Mode    | fs.readFile +---->| read() +-*                                   *->| Read file using NodeJs |
             +-------------+     +--------+  \                                 /   +------------------------+
                                              \                               / 
                                               \                             /
                                                \   +--------------------+  /
                                                 *->| allocate resources +-*
Kernel Mode                                         | for reading file   |
                                                    +--------------------+

```

Here is a simple diagram to understand how a System Call works.

In this example, when we call `fs.readFile()` in Node.js, the Node.js runtime (written in C and C++) internally calls the `read()` system call. The kernel then allocates the required resources or services to read the file.

I draw simple diagram for understand System Call, it this diagram i use NodeJs Example, when we call `fs.readFile()` for read file how it work!, NodeJs written in c and c++ when we call `fs.readFile()` function then NodeJs runtime call `read()` System Call using c and c++, abalitiy. and kernel allocate resources or services for read file.

And Operating System have many system such as `socket()`, `mmap2()`, `fork()`, etc...

- `socket()` use for Network I/O,
- `mmap2()` use to allocate memory for user space.
- `fork()` use to create child process.
- and more.

> This is [list](https://www.chromium.org/chromium-os/developer-library/reference/linux-constants/syscalls/) of System Calls in linux.

### Why do we need System Calls?

The Operating System is a complex program that allows us to use a computer.
It completes many algorithms for task scheduling, memory management, reading and writing data from drives, etc. It has full access to the hardware because it runs in kernel mode. It is the main driver of the computer and is responsible for managing all components.

If users directly access hardware, it can cause faults in kernel space. Therefore, user programs are not allowed to access hardware directly. Instead, they must request access through the kernel using system calls.

Before allocating any service or resource, the kernel checks multiple safety levels — such as whether the user is authorized, capable, and whether resources are available.
This makes hardware access safe and controlled, ensuring only limited and secure access for user programs.
