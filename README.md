La tâche 3 a été complètement automatiser en utilisant le Template fait par Lune Bellec (PhD)

# Airoh Template: Reproducible Pipelines Made Simple

_why don't you have a cup of relaxing jasmine tea?_

This repository provides a minimal, modular, and **fully reproducible** template for scientific workflows. Built on the [`invoke`](https://www.pyinvoke.org/) task runner, [datalad](https://www.datalad.org/) for data management as well as containerization tools (Docker or Apptainer), it lets you go from clean clone to output figures with just a few commands.

The logic is powered by [`airoh`](https://pypi.org/project/airoh/), a lightweight, pip-installable Python package of reusable `invoke` tasks. This repository runs small analyses just to demonstrate how the `airoh-template` works. It should be easy to adapt to a variety of other projects.

⚠️ **Status**: This template is in its early days. Expect rapid iteration and changes.

---

## ✨ TL;DR:

This repository is a [GitHub template](https://github.com/airoh-pipeline/airoh-template/generate). Click **“Use this template”** to create your own analysis project.
```bash
pip install -r setup.txt
invoke setup
invoke fetch
invoke run
```
Voilà — from clone to full reproduction.

---

## 🚀 Quick Start

### **Step 1**: Setup the project dependencies

If you are using `pip`, for instance in a virtual environment:
```
bash
pip install -r setup.txt
invoke setup
```
The initial call to `pip`is for core `airod` dependencies. The call to `invoke run` uses `pip install` under the hood with the provided requirements file, but that step can be made much more complex in `tasks.py`.

If you are using `conda`:
```
bash
conda env create -f environment.yml
conda activate brainbeats_pre
invoke setup
```
---
### **Step 2**: Fetch the source data

```
bash
invoke fetch
```

---

### **Step 3**: Run the analysis pipeline

```
bash
invoke run
```

This will execute a full analysis pipeline (simulation + figures).

---


## 🧠 Core Features

* Modular `tasks.py` that imports reusable code from `airoh`
* Minimal and readable `invoke.yaml` configuration file
* Optional containerization for full reproducibility
* Real output notebooks & figures — ready to publish


If you're working with Zenodo or other public sources, you can also configure `invoke.yaml` to fetch and extract archives via `invoke fetch`.

You can add entries under the `files:` section in `invoke.yaml` to automate downloads using `invoke fetch`.

By default, the template excludes `source_data/` and `output_data/` from Git. If you prefer to track them, you can manage them with Datalad instead.

---

## 🧰 Task Overview

| Task             | Description                                                    |
| ---------------- | -------------------------------------------------------------- |
| `setup`          | Installs Python dependencies from `requirements.txt`           |
| `fetch`          | Downloads dataset using Datalad and config in `invoke.yaml`    |
| `run`            | Executes Jupyter notebooks for each figure                     |
| `clean`          | Removes the `output_data_dir` contents                         |
| `docker-build`   | Builds a Docker image from the current repo                    |
| `docker-archive` | Archives the Docker image into a `.tar.gz` for sharing         |
| `docker-setup`   | Loads a prebuilt image from a `.tar.gz` archive (e.g., Zenodo) |
| `docker-run`     | Runs any task inside the Docker image                          |

Use `invoke --list` or `invoke --help <task>` for descriptions and usage.

---

## 🧭 Tips

* Use `invoke --complete` for tab-completion support
* Configure paths and data sources in `invoke.yaml`
* To use this template for a new project, start from [`airoh-template`](https://github.com/SIMEXP/airoh-template) and customize `tasks.py` + `invoke.yaml`

---

## 📁 Folder Structure

| Folder         | Description                              |
| -------------- | ---------------------------------------- |
| `notebooks/`   | Jupyter notebooks (e.g., one per figure) |
| `source_data/` | Raw source datasets                      |
| `output_data/` | Generated results and figures            |
| `tasks.py`     | Project-specific invoke entrypoint       |
| `invoke.yaml`  | Config file for all reusable tasks       |

---

## 🔁 Want to contribute?

Submit an issue or PR on [`airoh`](https://github.com/SIMEXP/airoh).

---

## Philosophy

Inspired by Uncle Iroh from *Avatar: The Last Airbender*, `airoh` aims to bring simplicity, reusability, and clarity to research infrastructure — one well-structured task at a time. It is meant to support a concrete implementation of the [YODA principles](https://handbook.datalad.org/en/latest/basics/101-127-yoda.html).

La réalisation de la tâche 3 a été assisté par l'ia
<img width="170" height="77" alt="image" src="https://github.com/user-attachments/assets/98185aa5-be64-4b19-8db4-05de6fd4f5c7" />
