# 🧠 What is Jupyter Notebook?

**Jupyter Notebook** is an open-source, browser-based interactive environment where you can **write and run code**, **see outputs immediately**, and **add explanations, equations, and visuals**—all in one place.

A Jupyter Notebook file (`.ipynb`) is made of **cells**:

* **Code cells** → run Python (or other languages)
* **Markdown cells** → write text, headings, formulas, notes
* **Output cells** → show results, charts, tables, images

It’s widely used in **data science, AI, and machine learning**.



## Why Jupyter Notebook is important for AI & ML (AIML)

#### 1️⃣ Interactive experimentation

AI/ML requires a lot of **trial and error**. Jupyter lets you:

* Run code **step by step**
* Modify one cell without re-running the entire program
* Instantly view outputs

This makes model experimentation fast and efficient.



#### 2️⃣ Perfect for data analysis & visualization

AI/ML starts with **data exploration**. Jupyter works seamlessly with:

* `NumPy`
* `Pandas`
* `Matplotlib`
* `Seaborn`

You can visualize data, clean it, and understand patterns **inline**.



#### 3️⃣ Ideal for machine learning workflows

With Jupyter you can:

* Load datasets
* Preprocess data
* Train ML models
* Evaluate accuracy
* Plot performance graphs

All inside a single notebook, in logical steps.



#### 4️⃣ Combines code + explanation (great for learning)

You can explain:

* What an algorithm does
* Why a parameter was chosen
* What the output means

This is **excellent for students, projects, and interviews**.



#### 5️⃣ Widely used in industry & research

Jupyter is used by:

* AI researchers
* Data scientists
* ML engineers
* Universities & online courses

Most **AI/ML tutorials, Kaggle notebooks, and research papers** use Jupyter.



#### 6️⃣ Comes with Anaconda (easy setup)

When you install **Anaconda**, you automatically get:

* Python
* Jupyter Notebook
* JupyterLab
* All major AI/ML libraries

No complex setup required.



➡️ Output appears **immediately below**, making analysis intuitive.


### Summary

| Feature              | Benefit for AIML          |
| -------------------- | ------------------------- |
| Interactive cells    | Faster experimentation    |
| Visualizations       | Better data understanding |
| ML libraries support | Easy model building       |
| Documentation + code | Clear learning & sharing  |
| Industry standard    | Career-relevant skill     |


### In short

👉 **Jupyter Notebook is installed for AIML because it makes learning, experimenting, visualizing, and explaining AI/ML models simple and powerful.**



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
## 📸 Screenshot Example: 
![Jupyter Notebook](assets/conda-create.png)

Activate it:

```bash
conda activate jupyter-env
```

You should now see:

```
(Base) -> (jupyter-env)
```
## 📸 Screenshot Example: 
![Jupyter Notebook](assets/conda-activate.png)


## 📦 Step 4: Install Jupyter Notebook (Correct Way)

```bash
conda install jupyter
```

✔ Installed inside `jupyter-env`

✔ No permission issues

✔ Safe and isolated

## 📸 Screenshot Example: 
![Jupyter Notebook](assets/conda-install.png)


## 🚀 Step 5: Run Jupyter Notebook

Start Jupyter:

```bash
jupyter notebook
```

Jupyter will run on:

```
http://localhost:8888
```
## 📸 Screenshot Example: 
![Jupyter Notebook](assets/jupyter-run.png)

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
## Example of Deleting Jupyter Notebook
![Jupyter Notebook ](assets/uninstall-jupyter1.png)
![Jupyter Notebook ](assets/uninstall-jupyter2.png)

## 🏁 Summary

- ✔ Never install heavy packages in `base`
- ✔ Always use a dedicated Conda environment
- ✔ Jupyter runs locally in your browser

Happy Coding 🚀

