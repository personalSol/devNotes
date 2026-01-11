---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2025-12-28T18:17
---
---

At the top level, we have **Miniconda** and **Anaconda**, which are two **Python distributions**.  
A _distribution_ means they bundle Python along with tools to manage packages and dependencies.

Both Miniconda and Anaconda come with **Conda**, which is an **environment and package management tool**.  
Conda helps create isolated environments and install/manage dependencies easily.

The main difference is that **Anaconda** comes with many preinstalled packages, while **Miniconda** is a minimal installation where you install only what you need.
- shouldn't directly delete a env as its metadata still remains
- named env get stored inside `~/miniconda3/envs/myenv`

- [[conda setup]]



conda supports **two kinds of environments**:

###### 1️⃣ Named environments (managed by conda)

- Stored in: `~/miniconda3/envs/<env_name>`
- Example: `conda create -n myenv python=3.11`

###### 2️⃣ Prefix (path-based) environments

- Created at an **explicit path**
- Example: `conda create -p /mnt/Main/Code/AI/ai_project/env python=3.11`
- These **do not have a name**
- They are identified only by their **directory path**

To see which dependencies we installed - 
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