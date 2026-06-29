# Midstate GPU Miner

Linux x86_64 binary release for the optimized Midstate GPU miner.

## Download and Run

```bash
curl -L https://github.com/VaniaHilkovets/midstate-gpu-miner/releases/latest/download/midstate-linux-x86_64 -o midstate \
  && chmod +x midstate \
  && ./midstate miner --pool-url stratum+tcp://rpc.cypherpunk.gold:3333 --payout-address <YOUR_PAYOUT_ADDRESS> --threads 1
```

Replace `<YOUR_PAYOUT_ADDRESS>` with your own payout address before mining.

## Notes

- Requires Linux x86_64.
- Uses the GPU backend automatically when a supported GPU/Vulkan adapter is available.
- The miner prints status automatically every 5 seconds.
