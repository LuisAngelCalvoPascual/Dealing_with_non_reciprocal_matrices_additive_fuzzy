README.txt

# Non-Reciprocity Analysis in Random Matrices

## Description
This project analyzes non-reciprocity measures in random square matrices of different sizes. It focuses on two types of matrices:
- **Fuzzy Preference Relation (FPR) matrices**: Square matrices where the diagonal entries are fixed at 0.5, and the off-diagonal elements are independently sampled from a continuous uniform distribution \( U(0.0001, 0.9999) \).
- **Additive Pairwise Comparison (APC) matrices**: Square matrices where all entries, including the diagonal, are independently sampled from a uniform distribution \( U(-100, 100) \).

For FPR matrices, the non-reciprocity measure \( \Upsilon \) is computed, while for APC matrices, the measure \( \Xi \) is used. Non-reciprocity is evaluated under three matrix norms:
- \( L_1 \) (Manhattan norm, \( p=1 \)),
- \( L_2 \) (Euclidean norm, \( p=2 \)),
- \( L_{\infty} \) (Maximum norm, \( p=\infty \)).

Percentiles of these non-reciprocity measures are calculated for each matrix type, size, and norm, and the evolution of these percentiles as the matrix size increases is analyzed.

## Data Generation
First, execute the notebook `code.ipynb`.

This notebook generates random square matrices of sizes:
\[
2 \times 2, 3 \times 3, 4 \times 4, 5 \times 5, 6 \times 6, 7 \times 7, 8 \times 8.
\]

For each matrix size:
- **100,000 matrices** are generated, split into **10 independent runs** of 10,000 matrices each, to enhance statistical robustness.
- For each matrix, the non-reciprocity measure \( \Upsilon \) (for FPR) or \( \Xi \) (for APC) is calculated.
- The following percentiles are computed:
  \[
  0.1\%, 1\%, 2\%, 3\%, 4\%, 5\%, 10\%, 20\%, 25\%, 50\% \text{ (median)}.
  \]
- The percentiles are computed independently in each of the 10 runs and then averaged across the runs to obtain robust and stable estimates.

Results are saved as Excel (`.xlsx`) files, one for each combination of:
- Matrix type (FPR or APC),
- Matrix size,
- Norm \( (p=1, 2, \infty) \).

Each Excel file contains the computed percentile values for each run, along with their averaged value.

## Visualization
To visualize the results, open and run the notebook `plot_pmetrics_percentiles.ipynb`.

This notebook:
- Loads the generated `.xlsx` files,
- Extracts the selected percentile values (1st, 5th, 10th, and 50th percentiles),
- Creates a comprehensive figure (`additive_fuzzy_percentiles.png`) that plots:
  - Percentile curves for non-reciprocity measures \( \Xi \) (APC) and \( \Upsilon \) (FPR) against matrix size.
- The figure includes six subplots:
  - Three for \( \Xi \) (one per norm),
  - Three for \( \Upsilon \) (one per norm).

Each curve represents how the percentile values of the non-reciprocity measures change as the matrix size increases from \( 2 \times 2 \) to \( 8 \times 8 \).

## Percentile Tables
Additionally, the notebook `tables.ipynb` processes the individual Excel outputs and consolidates the results into six summary tables:
- **Three tables** for FPR matrices (\( \Upsilon \)) — one for each norm,
- **Three tables** for APC matrices (\( \Xi \)) — one for each norm.

Each table presents:
- **Rows**: Matrix size \( n \in \{2, 3, 4, 5, 6, 7, 8\} \),
- **Columns**: Selected percentiles \( 0.1\%, 1\%, 2\%, 3\%, 4\%, 5\%, 10\%, 20\%, 25\%, 50\% \),
- **Values**: Averaged percentile values across the 10 runs.

The six tables are saved in a single Excel file named `percentile_tables_fuzzy_additive.xlsx`, with descriptive worksheet names:
- **Table 1**: Percentile tables of \( \Upsilon \) for FPR matrices, \( p=1 \),
- **Table 2**: Percentile tables of \( \Upsilon \) for FPR matrices, \( p=2 \),
- **Table 3**: Percentile tables of \( \Upsilon \) for FPR matrices, \( p=\infty \),
- **Table 4**: Percentile tables of \( \Xi \) for APC matrices, \( p=1 \),
- **Table 5**: Percentile tables of \( \Xi \) for APC matrices, \( p=2 \),
- **Table 6**: Percentile tables of \( \Xi \) for APC matrices, \( p=\infty \).

These tables provide a clear and structured overview of the behavior of the non-reciprocity measures across different matrix sizes and norms.

## Project Structure
```
code.ipynb                    # Notebook to generate matrices and compute percentiles
plot_pmetrics_percentiles.ipynb # Notebook to visualize the percentiles
tables.ipynb                   # Notebook to create consolidated percentile tables
fuzzy_2x2_p1.xlsx, additive_2x2_p1.xlsx, ...  # Output Excel files for each setup
percentile_tables_fuzzy_additive.xlsx_

