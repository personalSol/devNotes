---
status: teenager
related-links:
created: 1970-01-01T05:30
updated: 2025-10-25T14:31
---
---

### Virtual Environment in Python

#### 🧠 What is a Virtual Environment?

A **virtual environment** is an isolated space where you can install Python packages (like Django, Flask, etc.) without affecting your system's global Python installation.

Linux Mint and other Linux systems rely on Python for many internal tools. Installing or updating packages globally can break those tools. Hence, we use a virtual environment to keep our projects safe and independent.

NOTE: for using django my terminal must be using virutal envirnment, it is not necessary to create django or any other folder inside virutal envirnment folder to use virtual envirnment. Important thing is I just need to ativate venv in my terminal before running django commands.

---

#### ⚙️ Why is it Needed?

- Prevents conflicts between different project dependencies.
- Keeps your system Python clean and stable.
- Allows each project to use different Python or package versions.
- Lets you freely install, upgrade, or remove packages without admin rights.

---

#### 🚀 How to Create a Virtual Environment

1. **Install venv module (if not already installed):**
    ```bash
    sudo apt install python3-venv -y
    ```
    
2. **Create a project folder:**
    
    ```bash
    mkdir myproject
    cd myproject
    ```
    
3. **Create a virtual environment:**
    
    ```bash
    python3 -m venv venv
    ```
    
    > Here, the first `venv` is the module name and the second `venv` is the folder name. You can replace it with any name, e.g., `myenv`.
    
4. **Activate the virtual environment:**
    
    ```bash
    source venv/bin/activate
    ```
    
    Once activated, your terminal will show `(venv)` before the prompt.
    

---

#### 📦 Installing Packages

While inside the activated environment:

```bash
pip install django
```

All packages will be installed locally inside the `venv` folder.

---

#### 🧩 Check Environment Python

To verify which Python you're using:

```bash
which python
```

It should point to your project's `venv/bin/python`, not `/usr/bin/python3`.

---

#### 🛑 Deactivating the Virtual Environment

When you’re done working:

```bash
deactivate
```

This returns you to your system Python environment.

---

#### 🔄 Reactivating Later

Whenever you come back to your project:

```bash
cd myproject
source venv/bin/activate
```

---

#### 🧹 Optional: Removing the Environment

To delete the environment completely:

```bash
rm -rf venv
```

---

Using virtual environments is one of the most important Python practices — it keeps every project clean, portable, and safe from version conflicts.

