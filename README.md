# UV Setup Guide

## 1. Install UV

Follow the official installation guide:

https://docs.astral.sh/uv/getting-started/installation/

### Windows Installation

Run the following PowerShell command:

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### Verify Installation

```powershell
uv --version
```

---

## 2. Create a New Python Project

Initialise a new Python project:

```powershell
uv init
```

---

## 3. Create a Virtual Environment

```powershell
uv venv
```

This will create a `.venv` folder in your project directory.

---

## 4. Activate the Virtual Environment

### PowerShell

```powershell
.venv\Scripts\Activate.ps1
```

### Command Prompt

```cmd
.venv\Scripts\activate.bat
```

---

## 5. Create a Requirements File

Create a file named `requirements.txt` and add the required packages:

```txt
chromadb
jupyterlab
ipykernel
pandas
numpy
python-dotenv
```

---

## 6. Install Dependencies

Install packages from the requirements file:

```powershell
uv pip install -r requirements.txt
```

> **Note:** `uv pip install -r requirements.txt` is the recommended approach for installing dependencies from a requirements file.

Alternatively, to add packages to `pyproject.toml`:

```powershell
uv add chromadb jupyterlab ipykernel pandas numpy python-dotenv
```

---

## 7. Launch Jupyter Lab

```powershell
uv run jupyter lab
```

Or launch the classic Jupyter Notebook:

```powershell
uv run jupyter notebook
```

---

## 8. Verify the Environment

Create a notebook and run:

```python
import sys

print("Python Version:", sys.version)
print("Python Executable:", sys.executable)
```

You should see your project's `.venv` Python executable.