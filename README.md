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

### Outputs: repro-demo/conda-version
- analyze.py
- environment.yml

### Steps
1. Create a directory (mkdir) to practice using conda/mamba. Activate a new environment (mamba create --> conda activate) with packages python=3.12 pandas=2.2
2. Use a practice script [repro-demo/conda-version/analyze.py]
3. Export to environment for reproducibility (conda env export --from-history)
4. Test reproducibility
   - Delete environment and test it from scratch (python analyze.py)
5. Simulate errors using an incompatible package (add numpy-1.9) --> use AI to diagnose and fix
   - AI conversation documented in AI_USAGE.md


## Part 2 — Python environments with uv

### Outputs: repro-demo/uv-version
- pyproject.toml
- uv.lock

### Steps
1. Replicating Part 1 using UV instead.
2. Create a directory to practice UV. Initialize and pin pandas<3 (uv init --> uv add "pandas<3")
3. Print the projects specifications [repro-demo/uv-version/pyproject.toml]
4. Now remove the environment and test it's reproducibility agiain using uv-lock. It should print the same version as before.

## Part 3 — R environments with renv

### Outputs: repro-demo/renv-version
- analyze.R
- renv.lock
- activate.R
- 
### Steps:
1. Switch to RStudio. Using the terminal, create a new directory for R and initialize renv
2. Create your script [repro-demo/renv-version/analyze.R] and save it.
3. Snapshot your environment using renv::snapshot to create the lock file [repro-demo/renv-version/renv.lock]
4. Test reproducibility - tear down and reconstruct the environment
5. Run the R script from the locked environment. 

## Part 4 — Containers: putting it in a box

### Outputs: repro-demo/conda-version
- dockerfile

### Steps:
1. Write a docker file and save to the conda directory
2. Run the file using Docker, ensuring reproducibility in a container.


## Graduate Addendum - Workflow Commentary:



