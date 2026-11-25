# victory-fork (8 GB VRAM / 16 GB RAM)

Work-in-progress fork of [fxceless/victory-fork](https://github.com/fxceless/victory-fork) and [Marvisak/VIctory](https://github.com/Marvisak/VIctory), a compatibility layer that runs an Xbox Series title natively on Windows from user-supplied files.

**This repository contains no title files, code, assets, or screenshots.** See [docs/asset-policy.md](docs/asset-policy.md).

## Test Machine

- **OS:** Windows 11
- **CPU:** Intel Xeon E5-2680 v4 (14c/28t, Broadwell)
- **GPU:** NVIDIA GeForce RTX 5060 (8 GB VRAM, 32-lane waves)
- **RAM:** 16 GB DDR4

## Build

```powershell
cargo build --release -p victory
```

Diagnostics build:

```powershell
cargo build --profile diag --features diagnostics -p victory
```

## Recommended Settings (8 GB VRAM / 16 GB RAM, NVIDIA)

```powershell
$env:VICTORY_GAME_DIR = "path/to/title"
$env:VICTORY_DISPLAY_MODE = "1920x1080"
$env:VICTORY_RELAY = "2"
$env:VICTORY_WIDE_BACK = "1"
$env:VICTORY_CARD_BUFFERS_MIN_MB = "1"
$env:VICTORY_CARD_BUFFERS_MB = "512"
$env:VICTORY_CARD_REHASH_RUNS = "1"
$env:VICTORY_JOIN_COPIES = "1"
$env:VICTORY_SHADER_LOOP_LIMIT = "256"
$env:VICTORY_SKIP_PIPELINES = "eeed82b877b44b5f"
$env:VICTORY_TEXTURE_BUDGET_MB = "2800"
$env:VICTORY_LAZY_TEXTURES = "1"
$env:VICTORY_NO_WATCHDOG = "1"

.\target\release\victory.exe run "path/to/title.exe" --execute
```

## Credits & License

- [Marvisak/VIctory](https://github.com/Marvisak/VIctory) (GPL-3.0-or-later)
- [fxceless/victory-fork](https://github.com/fxceless/victory-fork) (GPL-3.0-or-later)
- [myokex/victory-amd](https://github.com/myokex/victory-amd), [mpDom/VIctory](https://github.com/mpDom/VIctory), and community PR contributors
- [XCL](https://github.com/ivall/xcl) (GPL-2.0-only, reference only)

Licensed under **GPL-3.0-or-later**. See [LICENSE](LICENSE).
