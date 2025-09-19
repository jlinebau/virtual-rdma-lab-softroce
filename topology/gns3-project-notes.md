# GNS3 RDMA Lab Topology Notes

## Overview

This lab simulates a leaf-spine topology with two RDMA-capable hosts (`rdma-1`, `rdma-2`) connected via virtual switches. A NAT node provides internet access for package installation and GitHub access.

## Components

- `rdma-1`: Ubuntu VM, SoftRoCE enabled
- `rdma-2`: Ubuntu VM, SoftRoCE enabled
- `nat`: GNS3 NAT node for outbound internet
- `switches`: 4 virtual switches simulating leaf-spine connectivity

## IP Addressing

- `rdma-1`: `192.168.122.11`
- `rdma-2`: `192.168.122.12`
- `nat01` : `192.168.122.1
- `LEAF-01`: `192.168.122.4` Optional SVI

## Notes

- Interfaces are bridged using GNS3 Ethernet links
- NAT node allows access for `apt install`, `wget`, and GitHub access
- MTU defaults to 1500; RDMA works without jumbo frames in this test
- Did go ahead and change the MTU between 9000 and 1500 just cause
