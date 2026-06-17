# Ramesh Sir Vehicle — Release Bundle

Branch: `ramesh_sir_vehicle` (both `bldc` and `vesc_tool`)

## Contents

| File | What it is | Notes |
|------|-----------|-------|
| `staryag2.bin` | Starya **G2** firmware (raw binary) | Flash via VESC Tool firmware upload |
| `staryag2.hex` | Same firmware, Intel HEX | For SWD/JTAG programmers |
| `staryag2.elf` | Same firmware with symbols | For debugging only |
| `VESC-Tool-macOS-arm64.zip` | VESC Tool desktop app | macOS Apple Silicon (arm64) |
| `SHA256SUMS.txt` | Checksums | Verify with `shasum -a 256 -c SHA256SUMS.txt` |

## Sources

- Firmware: `bldc` @ branch `ramesh_sir_vehicle`, board target `fw_staryag2`
- VESC Tool: `vesc_tool` @ branch `ramesh_sir_vehicle`, commit `e6c66326`

## Notes

- The firmware binaries here are the **Jun 14** build output. They were NOT
  regenerated from a clean build because the `build/` directory is owned by
  `root`; to produce a verified-fresh build, clear it (`sudo rm -rf build`)
  and run `make fw_staryag2`.
- The VESC Tool app is unsigned/un-notarized. On first launch macOS may block
  it: right-click → Open, or run
  `xattr -dr com.apple.quarantine "VESC Tool.app"`.

## To flash

1. Open VESC Tool → connect to the controller.
2. Firmware tab → Custom file → select `staryag2.bin` → upload.
