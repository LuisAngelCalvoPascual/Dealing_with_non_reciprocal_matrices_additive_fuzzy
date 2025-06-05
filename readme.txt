README.txt

Description
-----------
This project analyzes non-reciprocity measures in random square matrices of different sizes. It calculates percentiles of these measures for various matrix norms and visualizes how they evolve as the matrix size increases.

Data Generation
---------------
First, execute the notebook 'code.ipynb'.

This notebook generates random square matrices of sizes:
2×2, 3×3, 4×4, 5×5, 6×6, 7×7, and 8×8.

For each matrix size:
- 100,000 matrices are generated (split into 10 runs of 10,000 matrices each).
- The following percentiles are computed: 0.1%, 1%, 2%, 3%, 4%, 5%, 10%, 20%, 25%, and 50% (median).
- Three matrix norms are evaluated:
  - Norm 1 (Manhattan norm, p=1)
  - Norm 2 (Euclidean norm, p=2)
  - Norm ∞ (Maximum norm, p=∞)

Results are saved as Excel (.xlsx) files, one for each combination of matrix size and norm.

Visualization
-------------
To visualize the results, open and run the notebook 'plot_pmetrics_percentiles.ipynb'.

This notebook:
- Loads the generated .xlsx files.
- Extracts the selected percentile values.
- Creates a figure ('figure2.png') that plots:
  - Percentile curves for non-reciprocity measures Ξ and Υ against matrix size.
- The figure includes six subplots:
  - Three for Ξ (one per norm) and three for Υ (one per norm).

Project Structure
-----------------
code.ipynb                   # Notebook to generate matrices and compute percentiles
plot_pmetrics_percentiles.ipynb # Notebook to visualize the percentiles
n_2x2_p_1.xlsx, n_2x2_p_2.xlsx, n_2x2_p_inf.xlsx, ... # Output Excel files
figure2.png                   # Generated figure with percentile curves
README.txt

Requirements
------------
- Python 3.x
- Libraries:
  numpy
  pandas
  matplotlib
  openpyxl

You can install the required libraries with:
pip install numpy pandas matplotlib openpyxl


Author
------
Luis Ángel Calvo Pascual
