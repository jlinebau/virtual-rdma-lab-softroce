# RDMA Core Installation and Dependencies

This guide documents the installation of essential RDMA packages required to enable SoftRoCE and run RDMA benchmarks in a virtual lab.

---

## 🧠 Why This Matters

RDMA support in Linux depends on the `rdma-core` userspace library, which provides tools, headers, and utilities for working with RDMA verbs and connection management. Without it, tools like `ibv_devinfo`, `ib_send_bw`, and `rdma link` will fail or be unavailable.

---

## 🛠️ Installation Steps

### 1. Update Package Index

```bash
sudo apt update

### 2. Install RDMA Core and Utilities
sudo apt install rdma-core ibverbs-utils perftest


rdma-core: Core userspace RDMA libraries and tools

ibverbs-utils: Includes ibv_devinfo, ibv_rc_pingpong, etc.

perftest: Benchmarking tools like ib_send_bw, ib_send_lat

### 3. Verify Installation
ibv_devinfo


output expeted, If ibv_devinfo is missing, recheck that ibverbs-utils is installed.:
hca_id: rxe0
transport: InfiniBand



### 4 Alternatively Build from Source (if you must)

git clone https://github.com/linux-rdma/rdma-core.git
cd rdma-core
mkdir build
cd build
cmake ..
make
sudo make install

Note: This may require additional dependencies like cmake, libnl, and libudev.




