# Week 3

This folder holds the Week 3 kernel-module exercise.

## Contents

- `HelloWorld_Kernel/` - minimal loadable kernel module example
- `main.c` - small user-space hello-world program

## Suggested Flow

1. Build the kernel module inside `HelloWorld_Kernel/`.
2. Load it with `insmod`.
3. Confirm the message with `dmesg`.
4. Remove it with `rmmod`.

For the exact commands, see [`HelloWorld_Kernel/README.md`](./HelloWorld_Kernel/README.md).
