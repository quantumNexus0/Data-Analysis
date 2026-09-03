# Python Basics — Data Analytics Project Setup Notes

Personal reference notes for setting up a Python environment using Anaconda + Jupyter for learning Python basics / data analytics.

---

## 1. Install Anaconda

- Download and install **Anaconda** from the official site: https://www.anaconda.com/download
- Anaconda comes with `conda`, Python, Jupyter, and many pre-installed data science libraries.

---

## 2. Create Project Folder Structure

```
Data Analytics/
└── python/
    └── python basics/
        ├── notes.ipynb
        └── notes.py
```

**Steps:**
1. Create a main folder → `Data Analytics`
2. Inside it, create a folder → `python`
3. Inside `python`, create a subfolder → `python basics` (for learning Python fundamentals)
4. Inside `python basics`, create your working files:
   - `.ipynb` → for Jupyter Notebook (interactive, cell-by-cell code)
   - `.py` → for regular Python scripts

---

## 3. Create a Virtual Environment (using conda)

Open terminal inside the `python` folder and run:

```bash
conda create -p venv python==3.12
```

- `-p venv` → creates the environment in a folder named `venv` **inside the current directory** (instead of conda's default global location)
- `python==3.12` → sets the Python version for this environment

---

## 4. Activate the Environment

```bash
conda activate venv/
```

- This activates the environment so all installs (`pip install ...`) happen **only inside this environment**, not globally.
- You'll see `(venv)` appear before your terminal path once activated.

---

## 5. Install `ipykernel`

```bash
pip install ipykernel
```

- This is required so that **Jupyter Notebook can detect and use this conda environment as a kernel**.
- Without this, the notebook won't show your `venv` as a selectable kernel option.

---

## 6. Run Jupyter Notebook & Select Kernel

1. Open the `.ipynb` file (via VS Code / Jupyter Lab / Jupyter Notebook).
2. Click on **"Select Kernel"** (top-right in VS Code, or Kernel menu in Jupyter).
3. Choose **"Create/Select Python Environment"**.
4. Pick the environment you created → `venv` (the one created via `conda create -p venv`).
5. Run your cells — output will now use packages installed inside `venv`.

> ⚠️ Always double-check the correct kernel (`venv`) is selected, otherwise code may run using the wrong Python environment.

---

## 7. Create `requirements.txt`

Create a file named `requirements.txt` inside the project folder to keep track of all libraries needed — so the project can be set up easily in the future or by anyone else.

**Example (`requirements.txt`):**
```
numpy==1.26.4
pandas==2.2.2
matplotlib==3.8.4
seaborn==0.13.2
scipy==1.13.0
scikit-learn==1.4.2
jupyter==1.0.0
openpyxl==3.1.2
plotly==5.22.0
ipykernel==6.29.4
```

**Install all libraries in one command:**
```bash
pip install -r requirements.txt
```

**To generate this file automatically from your active environment (after installing everything):**
```bash
pip freeze > requirements.txt
```

---

## Quick Summary (Full Flow)

| Step | Command / Action |
|---|---|
| 1 | Install Anaconda |
| 2 | Create folder structure: `Data Analytics → python → python basics` |
| 3 | `conda create -p venv python==3.12` |
| 4 | `conda activate venv/` |
| 5 | `pip install ipykernel` |
| 6 | Open `.ipynb` → Select Kernel → choose `venv` |
| 7 | Create `requirements.txt` with all needed libraries + versions |
| 8 | `pip install -r requirements.txt` (to install everything at once) |

---
