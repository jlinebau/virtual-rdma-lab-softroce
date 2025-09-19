# Virtual RDMA Lab with SoftRoCE
(beware, I am learning the markup for github, this repo was done in haste so I could document as I went, will fix markup later)
This project documents the creation of a fully virtual RDMA lab using SoftRoCE, GNS3, and manual reconstruction of deprecated utilities. It simulates a leaf-spine topology with NAT access and benchmarks RDMA performance using `ib_send_bw`.

## Features

- Leaf-spine topology in GNS3
- SoftRoCE setup with manual `rxe_cfg` reconstruction
- RDMA interface mapping and verification
- Benchmarking with `ib_send_bw` and `ibv_rc_pingpong`
- Troubleshooting and annotated diagnostics

## Goals

- Showcase operational mastery and resourcefulness
- Preserve deprecated infrastructure knowledge
- Teach reproducible RDMA lab setup

## Getting Started

See [`setup/softroce-install.md`](setup/softroce-install.md) for installation steps.

## Author

Justin
