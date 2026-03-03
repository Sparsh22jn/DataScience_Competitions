# Setup Guide — Kaggle API + GitHub Sync

This guide walks you through connecting three things:
1. Kaggle API (download datasets, submit from terminal)
2. Kaggle → GitHub sync (auto-commit notebook versions)
3. Local VS Code environment (optional, for cleanup work)

---

## 1. Kaggle API Setup

### Step 1 — Get your API key
1. Go to [kaggle.com](https://kaggle.com) → click your profile picture → **Settings**
2. Scroll to **API** section → click **Create New Token**
3. This downloads a file called `kaggle.json`

### Step 2 — Place the key file
**Windows:**
```powershell
# Create the .kaggle folder in your home directory
New-Item -ItemType Directory -Path "$HOME\.kaggle" -Force

# Move the downloaded file there
Move-Item "$HOME\Downloads\kaggle.json" "$HOME\.kaggle\kaggle.json"
```

### Step 3 — Install the Kaggle package
```powershell
pip install kaggle
```

### Step 4 — Test it
```powershell
kaggle competitions list
```
You should see a list of active competitions. If you get an error, double-check the path to `kaggle.json`.

---

## 2. Download a Competition Dataset

```powershell
# Navigate into a competition folder
cd competitions/titanic

# Download the data
kaggle competitions download -c titanic -p data/

# Unzip
Expand-Archive -Path data/titanic.zip -DestinationPath data/
```

> The `data/` folder is in `.gitignore` — raw data is never committed to GitHub.

---

## 3. Kaggle → GitHub Sync (Most Important Step)

This feature lets Kaggle auto-commit a notebook to this repo every time you save a version. **No manual push needed.**

### Step 1 — Link your GitHub account to Kaggle
1. Go to [kaggle.com](https://kaggle.com) → **Settings** → **Linked Accounts**
2. Click **Link** next to GitHub and authorize

### Step 2 — Enable sync on a notebook
1. Open any notebook on Kaggle
2. In the top-right menu, click **File → Link to GitHub**
3. Select this repository (`SparshJain_Kaggle`)
4. Set the path to: `competitions/<slug>/notebooks/<notebook-name>.ipynb`
5. Tick **"Make notebook public"** if you want it visible on your profile

### Step 3 — Save versions
Every time you click **Save Version** in Kaggle, it will:
- Create a versioned snapshot on Kaggle
- Commit the `.ipynb` file to this repo at the path you set

---

## 4. Local VS Code Environment (Optional)

For writing Markdown, cleaning up notebooks, or refactoring scripts:

```powershell
# Install all common data science packages
pip install -r requirements.txt

# Install Jupyter extension in VS Code if not already installed
# Extension ID: ms-toolsai.jupyter
```

Then open any `.ipynb` from the `competitions/` folder directly in VS Code.

---

## 5. Quick Reference

| Task | Command |
|---|---|
| List competitions | `kaggle competitions list` |
| Download dataset | `kaggle competitions download -c <slug> -p data/` |
| Submit predictions | `kaggle competitions submit -c <slug> -f submission.csv -m "message"` |
| Check leaderboard | `kaggle competitions leaderboard -c <slug> --show` |

---

## 6. Gitignore Notes

The `.gitignore` is configured to exclude:
- `data/` — raw datasets (too large, re-downloadable via API)
- `*.csv` inside competition folders — same reason
- `__pycache__/`, `.ipynb_checkpoints/` — noise
- `kaggle.json` — never commit credentials

Notebooks (`.ipynb`) **are** committed — that's the whole point.
