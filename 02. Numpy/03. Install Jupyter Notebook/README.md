# 📓 Install Jupyter Notebook using Conda (Windows)

This guide explains **how to install Jupyter Notebook using Conda** on Windows and **why you should always create a new Conda environment instead of installing in `base`**.

It is written for **beginners** and based on a **real-world permission error scenario**.



## 🧱 Prerequisites

- Windows OS
- Anaconda or Miniconda installed
- Conda Prompt / Anaconda Prompt available

Check Conda installation:
```bash
conda --version
````



## 📂 Step 1: Navigate to Your Working Directory

```bash
ls
d:
cd DirectoryName
mkdir Jupyter
cd Jupyter
```



## ❌ Step 2: Installing Jupyter in `base` (What Went Wrong)

```bash
conda install jupyter
```

### ❗ Error Shown

```
EnvironmentNotWritableError
The current user does not have write permissions to the target environment.
environment location: D:\...\Anaconda
```



## ❓ Why This Error Occurs

* You were using the **`base` Conda environment**
* The base environment is installed in a **protected directory**
* Windows blocks write access
* Conda prevents unsafe modification of `base`

⚠️ This is **expected behavior**, not a bug.



## ✅ Step 3: Create a New Conda Environment (Recommended Way)

Create a new environment:

```bash
conda create -n jupyter-env
```

Activate it:

```bash
conda activate jupyter-env
```

You should now see:

```
(jupyter-env)
```



## 📦 Step 4: Install Jupyter Notebook (Correct Way)

```bash
conda install jupyter
```

✔ Installed inside `jupyter-env`
✔ No permission issues
✔ Safe and isolated



## 🚀 Step 5: Run Jupyter Notebook

Start Jupyter:

```bash
jupyter notebook
```

Jupyter will run on:

```
http://localhost:8888
```

A browser window will open automatically.



## 📸 Screenshot Example: Jupyter Running on Localhost

Add a screenshot showing Jupyter running in the browser:


![Jupyter Notebook running on localhost](assets/jupyter-localhost.png)


> **Figure:** Jupyter Notebook running locally at `http://localhost:8888` using a Conda environment.



## 📁 Recommended Project Structure

```
Installation/
├── README.md
└── assets/
    └── jupyter-localhost.png
```



## 🧠 Why You SHOULD Always Create a New Conda Environment

| Reason          | Explanation                           |
| --------------- | ------------------------------------- |
| 🔒 Safety       | Keeps base environment stable         |
| 🧩 Isolation    | Each project has its own dependencies |
| ⚙️ No Errors    | Avoids permission problems            |
| 🔁 Easy Cleanup | Delete and recreate anytime           |
| ✅ Best Practice | Recommended by Conda                  |

> **Rule:** One project = One Conda environment


## ❌ Why NOT Install Packages in `base`

* Base environment is shared
* High risk of dependency conflicts
* Hard to debug issues
* May require administrator permissions



## 🔁 Useful Conda Commands

Deactivate environment:

```bash
conda deactivate
```

List all environments:

```bash
conda env list
```

Remove an environment:

```bash
conda remove -n jupyter-env --all
```



## 🏁 Summary

 ✔ Never install heavy packages in `base`
 ✔ Always use a dedicated Conda environment
 ✔ Jupyter runs locally in your browser

Happy Coding 🚀

