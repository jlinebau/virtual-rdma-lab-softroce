
---

## Testing RDMA Client/Server

```markdown
# RDMA Benchmark: `ib_send_bw`

## Setup

- Server: `rdma-2`
```bash
ib_send_bw


#- Client: `rdma-1`
ib_send_bw 192.168.122.12


#- Successful output
BW average: 1.2 Gbps
Msg rate: 150K msg/sec
Other info confirming:
RDMA CM handshake succeeded

SoftRoCE stack fully operational