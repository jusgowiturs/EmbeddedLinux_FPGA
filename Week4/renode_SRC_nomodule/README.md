# renode_SRC_nomodule

Renode boot flow for the no-module setup.

## Contents

- `week4_zynq.resc` - Renode launch script
- `binfiles/vmlinux` - Linux kernel image used by Renode
- `binfiles/zynq-zed.dtb` - device tree blob
- `overlays/smarttimer_stub.repl` - MMIO placeholder overlay

## Flow

1. Start Renode with `week4_zynq.resc`.
2. The script creates a Zedboard-based machine.
3. It loads `vmlinux` and the device tree.
4. UART analyzers are enabled for console output.

## Purpose

This folder is the baseline Renode setup without the module-specific path.
