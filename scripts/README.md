# Benchmark scripts

Each script is self-contained and can be re-run from the repo root.

```bash
# Run any script directly:
bash scripts/<name>.sh

# Or override the GPU device:
DEVICE=cuda bash scripts/<name>.sh
```

## Scripts

| Script | What it runs | Cost (A100) |
|---|---|---|
| `benchmark_all.sh` | 9 backbones × 4 methods × 50 fixed images, zeros baseline → `results/benchmark_all/`. | ~3h |
| `benchmark_resnet50.sh` | ResNet50 only, 4 methods × 50 images, zeros baseline → `results/benchmark_resnet50/`. | ~15 min |

## Shared setup (`_common.sh`)

- Changes dir to repo root.
- Activates `.venv/` if present.
- Auto-picks `cuda` → `mps` → `cpu` (override via `DEVICE=...`).
