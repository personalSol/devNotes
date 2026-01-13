---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2026-01-11T19:56
---
---

after creating conda we need to create an environment. 

conda supports **two kinds of environments**:

###### 1️⃣ Named environments (managed by conda)

- Stored in: `~/miniconda3/envs/<env_name>`
- Example: `conda create -n myenv python=3.11`

###### 2️⃣ Prefix (path-based) environments

- Created at an **explicit path**
- Example: `conda create -p /mnt/Main/Code/AI/ai_project/env python=3.11`
- These **do not have a name**
- They are identified only by their **directory path**


```shell
# to see all conda env
conda env list

# to activate
conda activate <env name>

# to deactivate
conda deactivate


# to see which packages or dependencies we installed
conda env export --from-history

# to remove a conda env

# name based
conda env remove -n myenv

# path based
conda env remove -p /mnt/Main/Code/AI/ai_project/env

# to create a named env
conda create -n myenv python=3.11
conda activate myenv


```

```bash
conda create --prefix ./env pandas numpy matplotlib scikit-learn // to create a virtual environment name env and install these packages

// now to activate this environment
conda activate /mnt/Main/Code/AI/ai_project/env

// to see all available conda virtual environment
conda env list
```