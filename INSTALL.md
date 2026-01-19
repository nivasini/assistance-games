# Installation Guide

This guide provides tested installation instructions for running the assistance-games experiments on macOS (and likely Linux).

## Prerequisites

- Conda (Anaconda or Miniconda)
- Python 3.7 (required for TensorFlow 1.x compatibility)

## Option 1: Using Conda Environment File (Recommended)

```bash
# Create and activate the environment
conda env create -f environment.yml
conda activate assistance-games

# Install the package
pip install -e .
```

## Option 2: Manual Installation

```bash
# Create a new conda environment with Python 3.7
conda create -n assistance-games python=3.7 -y
conda activate assistance-games

# Install dependencies with specific compatible versions
pip install -r requirements.txt

# Install the package in development mode
pip install -e . --no-deps
```

## Known Issues and Solutions

### 1. opencv-python build failure on macOS
**Solution**: Use `opencv-python-headless` instead of `opencv-python`. This is already configured in the requirements.txt.

### 2. protobuf compatibility with TensorFlow 1.15
**Solution**: Use `protobuf==3.20.0`. Newer versions cause descriptor errors.

### 3. pyglet version incompatibility
**Solution**: Use `pyglet==1.5.27`. Version 2.x requires Python 3.8+.

### 4. gym/importlib-metadata compatibility
**Solution**: Use `importlib-metadata==4.13.0` to fix the `EntryPoints` attribute error.

## Verifying Installation

Test the installation by running a simple experiment:

```bash
python -m assistance_games.run -e mealchoice -a pbvi
```

You should see output showing the PBVI algorithm running and episode results.

## Running Experiments

See README.md for the full list of experiments to reproduce the paper results.
