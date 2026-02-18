# Artifact: Interpreting the Error of Differentially Private Median Queries through Randomization Intervals

This repository contains the official code, datasets, and pre-computed results for our paper. All core algorithm implementations, experiment pipelines, plotting scripts, and table generation functions are integrated into a single Jupyter Notebook for ease of use and reproducibility.

## 📁 Repository Structure

* `CI_clean.ipynb`: The main notebook containing all implementations, evaluation logic, and visualization code.
* `*.json`: Pre-computed experimental results across different datasets and $\epsilon$ values.
* `*.csv`: The raw datasets used for the experiments.

## 🛠️ Dependencies

Please ensure you have Python 3 installed along with the following standard scientific libraries. You can install them via pip:

```bash
pip install numpy pandas matplotlib tqdm
```
## 🚀 How to Reproduce the Results

Please open `CI_clean.ipynb` and run the setup/function definitions at the top. Once the environment is loaded, scroll down to the **very bottom of the notebook** where the execution blocks are located. You can choose any of the following actions:

### 1. Extract Metrics & Generate Tables (Fastest)
If you only want to view the final results (Mean and $\pm$ Std. Dev) presented in the paper's LaTeX tables, **you do not need to re-run the experiments**.
* **Action**: Scroll to the **"extract"** code block at the bottom of the notebook and run it.
* **Result**: It will read the provided `*.json` files and print neatly formatted metric tables directly matching the paper's findings.

### 2. Generate Plots
If you want to reproduce the visual charts (e.g., Median Error vs. Epsilon) with shaded error bars.
* **Action**: Scroll to the **"plot"** code block at the bottom and run it.
* **Result**: It will parse the existing `.json` data and generate the comparative performance plots shown in the paper.

### 3. Run Experiments from Scratch
If you wish to fully validate the code by re-running the algorithms from scratch.
* **Action**: Scroll to the **"Run experiment"** section at the bottom, configure your desired datasets or parameters (e.g., the $\epsilon$ list), and run the cell.
* **Result**: The code will execute both our method (`Our_EMCI`) and the baselines, evaluating their correctness and confidence interval lengths, and save the outputs as new `.json` files. 

> **⚠️ Note**: Running all experiments from scratch for all datasets may take a significant amount of time. For quick verification, we highly recommend using Option 1 or 2 with the provided pre-computed `.json` files.

## 📜 Credits & Acknowledgments

* **Base Implementation**: Our implementation is built upon and extends the code provided by [Sun et al. (2023)](https://github.com/PrivateCI/DP_CI). [cite_start]We have modified the domain handling and fixed specific logic errors as detailed in the paper.
* **Datasets**:
  * **Banking Dataset**: Sourced from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/bank+marketing).
  * **Adult Dataset**: Sourced from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/2/adult).
  * **Airplane Dataset**: This dataset was sourced from Kaggle (original URL currently unavailable). It contains aircraft specifications, including model, capacity, and price. We specifically evaluate the capacity attribute, which ranges from 4 to 396 with a true median of 162.

* **Documentation Note**: This README was refined with the assistance of large language models solely for improving language clarity and readability. The technical content, experimental logic, and codebase are the original work of the authors.