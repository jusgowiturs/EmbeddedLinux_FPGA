# Week 4

This folder contains Renode-based ARM Linux boot setups and sample user-space code.

## Contents

- `renode_SRC_module/` - Renode boot flow prepared for module testing
- `renode_SRC_nomodule/` - Renode boot flow without the module path
- `sample/` - simple C examples and compiled binaries

## Notes

The `renode_SRC_*` folders include:

- `week4_zynq.resc` - Renode script
- `binfiles/` - boot artifacts such as `vmlinux` and `zynq-zed.dtb`
- `overlays/` - board overlay descriptions

For folder-specific details, open the README in each subfolder.
