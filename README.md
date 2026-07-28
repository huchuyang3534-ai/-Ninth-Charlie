# AGDA Ocean-Acoustic Open Benchmark

This repository accompanies the manuscript:

**Acoustic-Guided Generative Assimilation for Estimating Ocean-Interior Structure From Surface and Acoustic Observations**

Target journal: IEEE Journal of Oceanic Engineering.

It is an open benchmark and audit package for acoustic-guided generative assimilation:
manuscript source, figure-generation scripts, compact processed result products, an
ACOBAR/Argo audit subset, and lightweight reproduction notes. It does not redistribute
large third-party raw archives.

## Download the full package

The complete package (manuscript, code, processed results, and audit data) is provided as a
downloadable archive on the **[Releases](../../releases)** page of this repository:

- `IEEE_JOE_AGDA_submission_package.zip` — full benchmark package.

Unzip it to obtain the following layout:

- `paper/`: review-format manuscript PDF/LaTeX, cover letter, metadata, checklist, figures.
- `code/05_code/`: main analysis and toy/OSSE experiment code.
- `code/figure_scripts/`: scripts to regenerate the Pareto-efficiency and physical-interpretability diagnostics.
- `code/acobar_scripts/`, `code/swellex96_scripts/`: ACOBAR consistency and SWellEx-96 negative-control scripts.
- `data/processed_results_06_results/`, `data/processed_results_13_GPU_package_diffusion/`: compact processed outputs used by the manuscript.
- `data/acobar_minimal_subset/`: author-generated ACOBAR validation outputs and the Argo selection list (raw ACOBAR products from NERSC are not redistributed).
- `reproducibility/`, `supplemental-notes/`: dependency notes, smoke tests, manifest, and data-use details.

## Reproduction

```powershell
pip install -r reproducibility\requirements.txt
python -B code\figure_scripts\make_paper2_mechanism_figures.py
cd paper
pdflatex main.tex
pdflatex main.tex
```

The full population OSSE and diffusion training runs are computationally heavier and are not
intended as smoke tests.

## Data scope

Raw HYCOM, Argo, SWellEx-96, ACOBAR, and Kuroshio Extension survey archives should be
obtained from their original providers. This repository includes compact processed products
and audit subsets used to reproduce or inspect the manuscript claims.

## License

Code is released under the MIT License (`LICENSE`). Author-generated processed data and
figures are released for research reuse under the terms in `DATA_LICENSE.md`; third-party
source data remain subject to their original licenses and terms of use.
