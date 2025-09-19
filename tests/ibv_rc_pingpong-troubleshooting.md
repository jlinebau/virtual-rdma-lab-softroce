
---

## RDMA PINGPONG

```markdown
# Troubleshooting `ibv_rc_pingpong`

## Errors Encountered

- `Failed to modify QP to RTR`
- `Couldn't connect to remote QP`
- `No space left on device`

## Diagnosis

- RDMA CM module was missing
- `rxe_cfg` script passed incorrect arguments
- Manual `rdma link add` resolved the issue

## Fix

```bash
sudo modprobe rdma_cm
sudo rdma link add rxe0 type rxe netdev ens3


Outcome
ib_send_bw worked; ibv_rc_pingpong remained unreliable due to RDMA CM quirks in SoftRoCE.