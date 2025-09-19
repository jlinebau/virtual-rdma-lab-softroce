# SoftRoCE Installation and RDMA Interface Setup

## Kernel Modules

```bash
sudo modprobe rdma_rxe
sudo modprobe rdma_cm



## Create the Soft RDMA interfaces


sudo rdma link add rxe0 type rxe netdev ens3
rdma link show

link rxe0/1 state ACTIVE physical_state LINK_UP netdev ens3


## RDMA Device Utils/Verfication

sudo apt install ibverbs-utils
ibv_devinfo

hca_id: rxe0
transport: InfiniBand




