# Midstate GPU Miner

Optimized Midstate GPU miner with multi-GPU support and batched dispatch for higher pool-effective hashrate.

## Download and Run

Mine through your own node/pool server on `82.38.4.87:3333`:

```bash
curl -L https://github.com/VaniaHilkovets/midstate-gpu-miner/releases/latest/download/midstate-linux-x86_64 -o midstate \
  && chmod +x midstate \
  && ./midstate miner --pool-url stratum+tcp://82.38.4.87:3333 --payout-address <YOUR_PAYOUT_ADDRESS> --threads 1
```

Mine through the public pool:

```bash
curl -L https://github.com/VaniaHilkovets/midstate-gpu-miner/releases/latest/download/midstate-linux-x86_64 -o midstate \
  && chmod +x midstate \
  && ./midstate miner --pool-url stratum+tcp://rpc.cypherpunk.gold:3333 --payout-address <YOUR_PAYOUT_ADDRESS> --threads 1
```

Replace `<YOUR_PAYOUT_ADDRESS>` with your own payout address before mining.


## Features

- Multi-GPU: automatically uses all discrete GPUs in parallel
- Batched dispatch: groups multiple k_step dispatches per submit for higher GPU utilization
- Streaming shares: each GPU submits found shares immediately
- Runtime tuning via `GPU_OC_SETTINGS.toml`:
  - `batch_nonces` (default 24576)
  - `iters_per_dispatch` (default 2000)
  - `steps_per_submit` (default 8)
  - `workgroup_size` (default 64, try 128 or 256)
  - `duty` (default 1.0)

## Notes

- Requires Linux x86_64 with Vulkan drivers installed.
- Dashboard prints every 5 seconds automatically.
- 12.6% faster than official miner by accepted shares on RTX 3090.
