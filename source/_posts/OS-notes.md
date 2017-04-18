---
title: OS notes
date: 2017-04-15 18:59:08
categories: [programming, unfinished]
tags: [OS]
---

# Operating System

This is the note or keywords of a course in udacity.

## Overview

- Processes and process management
- Threads and concurrency
- resource management
- OS services
- OS support for distributed services
- Data cendter and cloud

## Introduction

### OS Elements

Abstractions

- Process, thread, file, socket, memory pape

Mechanisms

- Create, schedule, open, write, allocate

Policies

- Least - recently used (LRU) etc.


### System call

Two ways for a user process to execute a priviledged call.

- User process calls hardware directly, and that will cause a trap, the kernel check if it is legal
- User process executes system call.

user/kernel transitions are not cheap!

### OS services

- Scheduler => CPU
- Mem manager
- Block device driver
- file system
- ...

### Linux Architecture

User interface : **Users** <= user mode

Library interface : **Standards utility programs** (shell, editor, compilors) <= user mode

System call interface : **Standard licrary** (open, close, read, write, fork) <= user mode

**Linux operating system** <= kernel mode

**Hardware**

## Processes and Process Management

A process:

- state of execution
  - Program counter
  - stack
- parts and temporary holding area
  - Data, register
- May require special hardware
  - IO devices

Process == state of a program when executing.

### Process Control Block (PCB)

a data structure storing status of a process

- PCB created when process is created
- Certain filds are updated when process state changes
- other fields change too frequently

### Context switch

Hot cache, cold cache

### CPU scheduler

OS must 

- preempt
- schedule
- dispatch

### Multi Processes

P1(web server), P2(Database)

Inter - process communication (IPC) : 

- Message - passing IPC


- Shared memory IPC