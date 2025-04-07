#  Installing FiftyOne


## Step 1: Install Miniconda or Anaconda
Conda is the recommended environment manager. If you don't already have Conda installed:

1. Download [Miniconda](https://docs.conda.io/en/latest/miniconda.html) (recommended for smaller footprint) or [Anaconda](https://www.anaconda.com/products/distribution)

2. Run the installer and follow the prompts

## Step 2: Create a Conda environment

Open your terminal or Anaconda Prompt and run:
```bash
conda create -n fiftyone python=3.11
```

This creates a new environment named "fiftyone" with Python 3.11 (compatible with FiftyOne).

## Step 3: Activate the environment

```bash
conda activate fiftyone
```
Your prompt should change to indicate the environment is active.

## Step 4: Install FiftyOne

Install FiftyOne using pip within the Conda environment:
```bash
pip install fiftyone
```

## Step 5: Verify installation

```bash
python -c "import fiftyone as fo; print(fo.__version__)"
```

This should print the FiftyOne version without errors.

## Step 6: Install dependencies

You can install the required dependencies for this workshop using the [`requirements.txt`](requirements.txt) in this repository

```bash
pip install -r requirements.txt
```

## Step 7: Quick test

Run a simple test to ensure everything works:
```python
import fiftyone as fo
import fiftyone.zoo as foz

# Load a small sample dataset
dataset = foz.load_zoo_dataset("quickstart")

# Launch the app to explore it
session = fo.launch_app(dataset)
```

## Working with your FiftyOne installation

- To use FiftyOne later, always activate the environment first: `conda activate fiftyone`
- To upgrade FiftyOne: `pip install --upgrade fiftyone`
- To deactivate when finished: `conda deactivate`

## Troubleshooting

- If installation fails, try: `pip install --upgrade pip setuptools wheel build`

- For platform-specific issues, refer to the [FiftyOne documentation](https://beta-docs.voxel51.com/getting_started/basic/install/#troubleshooting)

- Mac users may need XCode Command Line Tools

- Linux users might need additional packages like `python3-dev`

This conda-based installation creates an isolated environment that won't interfere with your other Python projects, making it easy to manage dependencies and keep your FiftyOne setup clean.

You can [read these docs for more detail](https://beta-docs.voxel51.com/fiftyone_concepts/running_environments/) about setting up your enviornment.