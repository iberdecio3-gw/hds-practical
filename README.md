## Lab 1: repro-demo

```text
hds-practical/
├── README.md
├── .gitignore
├── repro-demo
    ├── Conda Version
        ├── environment.yml
        ├── analyze.py
        ├── Dockerfile
    ├── UV Version
        ├── uv.lock
        ├── pyproject.toml
        ├── python-version
        ├── src/uv_versioin
            ├── __init__.py
    ├── Renv Version
        ├── renv.lock
        ├── analyse.R
        ├── renv-version
            ├── .gitignore
            ├── activate.R
            ├── settings.json
├── src/
    ├── analyze.R
    ├── analyze.py
├── data/
└── AI_USAGE.md
```

## Part 1 — Python environments with conda/mamba 

# Outputs: repro-demo/conda-version
- analyze.py
- environment.yml

# Steps
1. Create a directory (mkdir) to practice using conda/mamba. Activate a new environment (mamba create --> conda activate) with packages python=3.12 pandas=2.2
2. Use a practice script [repro-demo/conda-version/analyze.py]
3. Export to environment for reproducibility (conda env export --from-history)
4. Test reproducibility
   - Delete environment and test it from scratch (python analyze.py)
5. Simulate errors using an incompatible package (add numpy-1.9) --> use AI to diagnose and fix
   - AI conversation documented in AI_USAGE.md


## Part 2 — Python environments with uv

## Part 3 — R environments with renv

## Part 4 — Containers: putting it in a box
