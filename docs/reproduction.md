# Reproduction workflow

This document keeps only the settings and commands needed to reproduce the
training variants and retrieval evaluation. Generated datasets, checkpoints,
logs, raw evaluation records, and intermediate tables are intentionally not
versioned.

## Common training settings

| Setting | Value |
| --- | --- |
| Epochs | 20 |
| Text learning rate | `1e-5` |
| Molecule learning rate | `1e-5` |
| Target temperature | `0.1` |
| Prediction temperature | `0.1` |
| Maximum candidate rank | `50` |
| Replacement probability | `0.5` |
| ER-loss weight | `1.0` or `2.0` |
| Global batch size | `30` |
| Maximum text length | `512` |

## Augmentation variants

### Baseline

The baseline samples uniformly from the precomputed top-50 Tanimoto neighbors.

```bash
GPU_IDS=0,1,2 ./sh/pretrain_baseline_ddp_3gpu.sh
```

### Curriculum

The curriculum uses the top-10 neighbors for epochs 1–5, expands the active
prefix linearly during epochs 6–15, and uses the full top-50 for epochs 16–20.
Sampling within the active prefix is uniform.

```bash
GPU_IDS=0,1,2 ./sh/pretrain_curriculum_ddp_3gpu.sh
```

### Stratified

The stratified variant samples from three rank groups:

| Group | Ranks | Probability |
| --- | ---: | ---: |
| High | 1–10 | 0.50 |
| Mid | 11–40 | 0.35 |
| Low | 41–50 | 0.15 |

Candidates below Tanimoto similarity `0.25` are rejected. If the selected group
has no eligible candidate, the original molecule is retained.

```bash
GPU_IDS=0,1,2 ./sh/pretrain_stratified_ddp_3gpu.sh
```

Set `ALPHA=2.0` to run the alpha-2 variants. Run names, log paths, and
checkpoint paths can be overridden through the environment variables supported
by each shell script.

## Retrieval evaluation

The reproduction evaluator supports Description, Pharmacodynamics, and ATC
retrieval in both directions at candidate counts 4, 10, and 20.

```bash
python scripts/evaluate_retrieval_reproduction.py --help
```

Its raw output is written below `Reproduction_Evaluation/` by default and is
ignored by Git.