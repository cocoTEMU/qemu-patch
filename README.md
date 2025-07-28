# QEMU Patch for MMIO Stub Devices

This patch extends QEMU's Xilinx Zynq-A9 machine to support MMIO stub devices. It loads a user-provided Device Tree Blob (DTB) for Programmable Logic (PL) devices and creates stubs that proxy MMIO reads/writes over character devices (e.g., sockets). This enables co-simulation of AXI IP blocks, such as with cocoTEMU.

## Installation

1. Clone QEMU:  
```
git clone https://github.com/qemu/qemu.git
cd qemu
```

2. Apply the patch:  
```
curl https://raw.githubusercontent.com/cocoTEMU/qemu-patch/refs/heads/main/qemu.patch | git apply
```

3. Build QEMU from sources:
```
./configure --enable-slirp --enable-kvm --enable-vnc --enable-spice
make -j$(nproc)
sudo make install
```

## Usage

TODO
