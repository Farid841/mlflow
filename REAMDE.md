## 🎨 Part 1: Presentation

A presentation created with Slidev to explain MLflow in a visual and engaging way.

### 📋 Prerequisites

- **Node.js 20+**
- **npm** or **yarn** or **pnpm**
- Web browser

### 🚀 Installation and launch

1. Go to the presentation folder

```bash
cd presentation
```

2. Install dependencies
```bash
npm install
# or
yarn install
# or
pnpm install
```

3. Launch the presentation in development mode
```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

4. Open in browser:
http://localhost:3030

### 🎯 Useful commands

Development mode (with hot reload)

```bash
npm run dev
```

Build for production
```bash
npm run build
```

Preview the build
```bash
npm run preview
```

## 📚 Part 2: Tutorials

Practical tutorials with Jupyter notebooks to learn MLflow by practicing.

### 📋 Prerequisites

- **Python 3.10+**
- **Jupyter Notebook/Lab**
- **Git** (to clone the repository)

### 🚀 Installation and configuration

1. Go to the tutorials folder

```bash
cd tutorials
```

2. Create a Python virtual environment
```bash
python -m venv env
```

3. Activate the virtual environment
```bash
# On Linux/Mac:
source env/bin/activate
# On Windows:
env\Scripts\activate
```

4. Install dependencies
```bash
pip install -r requirements.txt
```

5. Start Jupyter Lab or use it throught VScode
```bash
jupyter lab
# or for Jupyter Notebook
jupyter notebook
```

### 📖 Tutorial content

#### 🏃‍♂️ Quick start
- **`tracking_quickstart_1.ipynb`** - Introduction to basic concepts
- **`logging-first-model_2.ipynb`** - First model with MLflow

#### 📚 Step-by-step detailed guide
The `step_by_setp_with_documentation_screenshoot/` folder contains:

**Experiment management:**
- `1_1_experiments_create_experiments.ipynb` - Creation
- `1_2_experiments_retrieve_experiments.ipynb` - Retrieval
- `1_3_experiments_update_experiments.ipynb` - Update
- `1_4_experiments_delete_experiments.ipynb` - Deletion

**Run management:**
- `2_1_runs_create_run.ipynb` - Creation
- `2_2_runs_retrieve_run.ipynb` - Retrieval
- `2_3_runs_update_run.ipynb` - Update
- `2_4_runs_nested_runs.ipynb` - Nested runs
- `2_5_runs_delete_run.ipynb` - Deletion

### 🎯 How to get started

1. Start the MLflow server (in a separate terminal)
```bash
mlflow ui
```

2. Open Jupyter (in another terminal)
```bash
jupyter lab
```

# You're ready to start

🔗 Useful links

- [Official MLflow Documentation](https://mlflow.org/docs/latest/)
- [MLflow on GitHub](https://github.com/mlflow/mlflow)
- [Slidev Documentation](https://sli.dev/)
- [Jupyter Documentation](https://jupyter.org/documentation)

---

**Happy learning with MLflow! 🎉**