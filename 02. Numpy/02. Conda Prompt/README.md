# 🐍 Conda Prompt Basics (Beginner Notes)

This guide explains **basic Conda commands** using real examples from the Conda Prompt on **Windows**.  
Perfect for beginners starting with **Python, AI/ML, or Data Science**.



## 📌 What is Conda?

**Conda** is a package and environment manager that helps you:
- Manage **Python versions**
- Install packages safely
- Create **isolated environments** for different projects



## 🖥️ Understanding the Conda Prompt

When you open **Anaconda Prompt**, you may see:

```text
(base) C:\Users\tyagi>
```

- `(base)` → currently active Conda environment  
- `base` is the **default environment**



## 🔹 Check Conda is Installed

```bash
conda
```

To check version:

```bash
conda --version
```

Example output:
```text
conda 25.11.1
```



## 📦 List Installed Packages

```bash
conda list
```

- Shows all packages installed in the **current environment**
- Useful to check libraries like `numpy`, `pandas`, `scikit-learn`, etc.



## 🌱 Create a New Environment

```bash
conda create -n AIML
```

- `-n AIML` → environment name
- Creates a **clean environment**



## ▶️ Activate an Environment

```bash
conda activate AIML
```

Prompt changes to:

```text
(AIML) C:\Users\tyagi>
```



## 📋 List All Environments

```bash
conda env list
```

- `*` indicates the active environment



## ⚠️ Environment Name is Case-Sensitive

```bash
conda create -n aiml
```

- `AIML` and `aiml` are treated as **different environments**



## ❌ Remove an Environment (Correct Way)

You **cannot delete an active environment**.

### ✅ Correct Steps

```bash
conda deactivate
conda remove -n aiml --all
```



## 🔁 Final Environment Check

```bash
conda env list
```


## ✅ Summary of Useful Commands

| Purpose | Command |
|------|------|
| Check Conda | `conda` |
| Version | `conda --version` |
| List packages | `conda list` |
| Create env | `conda create -n ENV_NAME` |
| Activate env | `conda activate ENV_NAME` |
| Deactivate env | `conda deactivate` |
| List envs | `conda env list` |
| Delete env | `conda remove -n ENV_NAME --all` |



## 🎯 Best Practice

- One environment per project
- Keep `base` clean
- Use clear environment names
