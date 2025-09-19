
---

## rxe_cfg Reconstruction

```markdown
# Reconstructing `rxe_cfg` Utility

## Problem

The `rxe_cfg` script was removed from the upstream `rdma-core` repo. Attempts to download it from historical commits or tags resulted in 404 errors.

## Solution
Save as rxe_cfg, make exe and move to /usr/bin

Manually recreated the script using known syntax:

```python
#!/usr/bin/env python3
import sys, subprocess

def run(cmd):
    print(f"> {cmd}")
    subprocess.run(cmd.split())

def usage():
    print("Usage: rxe_cfg [start|stop|add <iface>|remove <iface>|status]")

if len(sys.argv) < 2:
    usage()
    sys.exit(1)

action = sys.argv[1]

if action == "start":
    run("modprobe rdma_rxe")
elif action == "stop":
    run("rmmod rdma_rxe")
elif action == "add" and len(sys.argv) == 3:
    run(f"rdma link add {sys.argv[2]} type rxe netdev {sys.argv[2]}")
elif action == "remove" and len(sys.argv) == 3:
    run(f"rdma link del {sys.argv[2]}")
elif action == "status":
    run("rdma link show")
else:
    usage()
