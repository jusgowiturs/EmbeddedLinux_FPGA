# HelloWorld Kernel Module

This folder contains a minimal Linux kernel module named `helloworld`.

## Files

- `helloworld.c` - module source with `init` and `exit` handlers
- `Makefile` - external module build file
- `helloworld.ko` - built module artifact
- `helloworld.mod.c`, `helloworld.mod.o`, `helloworld.o`, `modules.order`, `Module.symvers` - generated build outputs

## Build Flow

`KDIR` must point to the Linux kernel build tree that matches the target kernel.  
For example, if you have a kernel source/build directory with `vmlinux`, headers, and generated symbols:

```bash
export KDIR=/path/to/kernel/build
make
```

What the Makefile does:

```bash
make -C "$KDIR" M="$PWD" INSTALL_MOD_PATH=/tmp/initramfs modules_install
ls /tmp/initramfs/lib/modules/6.6.0/updates/helloworld.ko 
cd $KDIR
make -j8  # Rebuild to embedded initramfs with updated kernel module
```

This compiles the module against the running or target kernel build tree and produces `helloworld.ko` under /tmp/initramfs/lib/.

## Load And Unload

Load the module:

```bash
sudo insmod helloworld.ko     # If not works give complete path
```

Check kernel logs:

```bash
dmesg | tail
```

Unload the module:

```bash
sudo rmmod helloworld
dmesg | tail
```

## Expected Messages

When loaded, the module prints:

```text
Hello: Kernel module loaded
```

When unloaded, it prints:

```text
Hello: Kernel module unloaded
```

## Cleanup

```bash
make clean
```
