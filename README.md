# Known-Good-Die from Certificate of Conformance

> **Automated KGD extraction and Gaussian distribution fitting from CoC PDFs**

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

## Overview

This tool automates the extraction of **Known Good Die (KGD)** integer values from semiconductor **Certificate of Conformance (CoC)** PDFs. After extraction, the values are statistically modeled by fitting a **Gaussian (normal) distribution**, enabling yield analysis and process capability assessments.

## Features

- **Batch PDF Processing** — scans an entire folder of CoC PDFs in one run
- **Robust Parsing** — locates "Known Good Die" headers and extracts the second numeric value per entry (handles multi-number rows automatically)
- **Gaussian Fitting** — fits a normal distribution to the extracted dataset using NumPy/SciPy
- **Excel Export** — saves all extracted values to `kgd_values_number.xlsx` via pandas
- **Console Signature** — displays developer info and initializes cleanly on Windows terminals

## Requirements

```
pdfplumber
pandas
numpy
matplotlib
openpyxl
```

Install dependencies:

```bash
pip install pdfplumber pandas numpy matplotlib openpyxl
```

## Usage

```bash
python "Known Good Die from COC"
```

When prompted, enter the path to the folder containing your CoC PDF files (or press **Enter** to use the current directory).

### Example output

```
System initializing...
Processing lot_A_coc.pdf  → KGD: 2500
Processing lot_B_coc.pdf  → KGD: 2480
...
Gaussian μ = 2490.3,  σ = 12.7
Results saved to kgd_values_number.xlsx
```

## Output Files

| File | Description |
|---|---|
| `kgd_values_number.xlsx` | All extracted KGD values with source file and page references |

## Author

**Engin Can Cicek**
