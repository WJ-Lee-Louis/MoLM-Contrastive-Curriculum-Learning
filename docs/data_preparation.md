# PubChem324kV2 data preparation

The data pipeline uses a separate CPU environment so the legacy AMOLE training
environment remains unchanged. Generated data is written below `data/` and is
ignored by Git.

```bash
export MICROMAMBA=/path/to/micromamba
export DATA_ENV=/path/to/amole-data
export TRAIN_ENV=/path/to/amole-train

"$MICROMAMBA" create -y -f environment-data.yml -p "$DATA_ENV"
bash scripts/download_pubchem324kv2.sh
"$MICROMAMBA" run -p "$DATA_ENV" python scripts/prepare_pubchem324kv2.py
"$MICROMAMBA" run -p "$DATA_ENV" \
  python scripts/validate_pubchem324kv2.py --validate-sdf
```

The source revision is fixed to
`e449660d39ec83c4ccf0bff2dcfb9bbf6943ab89`. The preparation script builds a
seeded 50,000-molecule subset, removes overlap with official evaluation splits,
preserves multi-description molecules, and records checksums and quality
statistics.

After reviewing the generated manifest and quality flags, create the
AMOLE-compatible graphs and fingerprints:

```bash
"$MICROMAMBA" run -p "$TRAIN_ENV" python scripts/finalize_amole50k.py
"$MICROMAMBA" run -p "$TRAIN_ENV" python scripts/validate_amole50k.py
```

Finally, compute exact self-excluded top-100 Tanimoto neighbors:

```bash
"$MICROMAMBA" run -p "$TRAIN_ENV" \
  python scripts/compute_tanimoto_topk.py --gpus 0,1,2,3 --k 100
```

The finalized package is created at `data/PubChemSTM_50k`. A compatibility
symlink named `data/PubChemSTM` may point to that directory.
