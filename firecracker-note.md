

> Written with [StackEdit](https://stackedit.io/).

kvm permission
```
sudo setfacl -m u:${USER}:rw /dev/kvm
```

start
```
rm -rf /tmp/firecracker.socket && ./build/debug/firecracker
```

build and test
```
tools/devtool build
tools/devtool build --release
tools/devtool test
```

example image (alpine-linux-3.8)
```
curl -fsSL -o hello-vmlinux.bin https://s3.amazonaws.com/spec.ccfc.min/img/hello/kernel/hello-vmlinux.bin
```
example rootfs
```
curl -fsSL -o hello-rootfs.ext4 https://s3.amazonaws.com/spec.ccfc.min/img/hello/fsfiles/hello-rootfs.ext4
```

docs: https://github.com/firecracker-microvm/firecracker/tree/master/docs

how to customize kernel image and rootfs?
https://github.com/firecracker-microvm/firecracker/blob/master/docs/rootfs-and-kernel-setup.md

how to setup network?
https://github.com/firecracker-microvm/firecracker/blob/master/docs/network-setup.md



<!--stackedit_data:
eyJoaXN0b3J5IjpbMzA1OTc3NTk0LDE5NDk1ODUxODIsMTk0OT
U4NTE4Ml19
-->