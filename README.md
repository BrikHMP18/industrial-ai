# Topics H - Setup

## 1. Install Conda

- **Linux:** `wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh && bash Miniconda3-latest-Linux-x86_64.sh`
- **Windows:** Download [Miniconda](https://docs.conda.io/en/latest/miniconda.html) (`.exe` installer)

Restart the terminal after installing.

## 2. Create environment and install

```bash
# Create environment with Python 3.12
conda create -n temas_h python=3.12 -y

# Activate (same command on Linux and Windows)
conda activate temas_h

# Install everything from requirements
pip install -r requirements.txt
```

## 3. Jupyter kernel

```bash
python -m ipykernel install --user --name=temas_h
```

## 4. GitHub (repo `industrial-ai`)

**Install Git:**
- **Linux:** `sudo apt install git` (Ubuntu/Debian) or `sudo dnf install git` (Fedora)
- **Windows:** Download [Git](https://git-scm.com/download/win)

**First time, configure identity:**
```bash
git config --global user.name "Your name"
git config --global user.email "your@email.com"
```

### Option A: Clone the repo (if it already exists on GitHub)

You get a copy of the project on your machine:

```bash
git clone https://github.com/USER/industrial-ai.git
cd industrial-ai
```

Replace `USER` with your GitHub username (e.g. `BrikHMP18`).

### Option B: Link a new local project to GitHub

If you already have the project folder on your PC and created an empty repo on GitHub (e.g. `https://github.com/USER/industrial-ai`):

1. Go to the project folder:
   ```bash
   cd /path/to/your/project
   ```

2. Initialize Git, create the first commit and link the remote (replace `USER` with your GitHub username):
   ```bash
   git init
   git branch -M main
   git remote add origin https://github.com/USER/industrial-ai.git
   git add .
   git commit -m "Initial commit: industrial-ai project"
   git push -u origin main
   ```

3. Verify on `https://github.com/USER/industrial-ai` that the files were pushed.

### Option C: Unlink and start from scratch

If your folder was linked to **another** repo or you want to delete all Git history and link it again:

1. Remove Git from the project (does not delete your files, only the `.git` folder):
   ```bash
   cd /path/to/your/project
   rm -rf .git
   ```

2. Follow the steps in **Option B** (from `git init` through `git push -u origin main`), using your username and the correct repo (`USER/industrial-ai`).

## 5. Cursor

- Download: https://cursor.com
