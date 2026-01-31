# Temas H - Setup

## 1. Instalar Conda

- **Linux:** `wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh && bash Miniconda3-latest-Linux-x86_64.sh`
- **Windows:** Descargar [Miniconda](https://docs.conda.io/en/latest/miniconda.html) (instalador `.exe`)

Reiniciar terminal tras instalar.

## 2. Crear entorno e instalar

```bash
# Crear entorno con Python 3.12
conda create -n temas_h python=3.12 -y

# Activar (mismo comando en Linux y Windows)
conda activate temas_h

# Instalar todo desde requirements
pip install -r requirements.txt
```

## 3. Jupyter kernel

```bash
python -m ipykernel install --user --name=temas_h
```

## 4. GitHub (repo `industrial-ai`)

**Instalar Git:**
- **Linux:** `sudo apt install git` (Ubuntu/Debian) o `sudo dnf install git` (Fedora)
- **Windows:** Descargar [Git](https://git-scm.com/download/win)

**Primera vez, configurar identidad:**
```bash
git config --global user.name "Tu nombre"
git config --global user.email "tu@email.com"
```

### Opción A: Clonar el repo (si ya existe en GitHub)

Obtienes una copia del proyecto en tu máquina:

```bash
git clone https://github.com/USER/industrial-ai.git
cd industrial-ai
```

Sustituye `USER` por tu usuario de GitHub (ej: `BrikHMP18`).

### Opción B: Vincular un proyecto local nuevo a GitHub

Si ya tienes la carpeta del proyecto en tu PC y creaste un repo vacío en GitHub (ej: `https://github.com/USER/industrial-ai`):

1. Entra a la carpeta del proyecto:
   ```bash
   cd /ruta/a/tu/proyecto
   ```

2. Inicializa Git, crea el primer commit y vincula el remoto (sustituye `USER` por tu usuario de GitHub):
   ```bash
   git init
   git branch -M main
   git remote add origin https://github.com/USER/industrial-ai.git
   git add .
   git commit -m "Initial commit: proyecto industrial-ai"
   git push -u origin main
   ```

3. Verifica en `https://github.com/USER/industrial-ai` que se subieron los archivos.

### Opción C: Desvincular y empezar de cero

Si tu carpeta estaba vinculada a **otro** repo o quieres borrar todo el historial de Git y volver a vincularla:

1. Eliminar Git del proyecto (no borra tus archivos, solo la carpeta `.git`):
   ```bash
   cd /ruta/a/tu/proyecto
   rm -rf .git
   ```

2. Seguir los pasos de **Opción B** (desde `git init` hasta `git push -u origin main`), usando tu usuario y el repo correcto (`USER/industrial-ai`).

## 5. Cursor

- Descargar: https://cursor.com
