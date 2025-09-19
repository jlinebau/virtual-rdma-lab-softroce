
---

## Notes Tshooting

```markdown
# Annotated Troubleshooting Log

## GitHub 404s

Attempted:
```bash
wget https://raw.githubusercontent.com/linux-rdma/rdma-core/master/softrdma/rxe_cfg
ERROR 404: Not Found

git checkout 41bbb0bed7a781be59e8c0dcd8b7278af2ce6882
fatal: reference is not a tree

Fixes
Reconstructed rxe_cfg manually

Used direct rdma link add commands

Verified with ibv_devinfo and ib_send_bw