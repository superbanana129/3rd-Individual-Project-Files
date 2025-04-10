
# Metamaterial Layout Optimization with GDSTK and Genetic Algorithms

## Introduction
This project explores the automated generation and optimization of metamaterial structures on flexible substrates using Python. It leverages the `gdstk` library for layout design in GDSII format and utilizes genetic algorithms to evolve optimal designs based on custom performance metrics.

The project consists of:
- Layout generation via GDSTK (`fan_generation.ipynb`)
- Data processing and feature extraction (`data_processing.ipynb`)
- Custom GA functionality (`GA_functions.ipynb`)
- Integration and orchestration code (`updated_code.ipynb`)

## Project Overview
The primary objective is to simulate and optimize micro-scale metamaterial patterns using polygonal geometries. These designs are structured in a hierarchical format (via GDSTK cells) and can be exported to standard GDSII layout files for fabrication.

![Demo layout output](assets/sample_layout.png)  
*Sample fan-shaped layout structure generated during optimization.*

## Installation Instructions

### Prerequisites
- Python 3.8+
- pip
- Jupyter Notebook

### Required Packages
Install the necessary packages via pip:

```bash
pip install numpy gdstk matplotlib pandas pygad
```

Ensure Jupyter is available:

```bash
pip install notebook
```

## How to Run the Code

1. **Launch Jupyter Notebook**:
```bash
jupyter notebook
```

2. **Run Each Notebook**:
   - `fan_generation.ipynb`: Generates initial and evolved geometries using `gdstk`.
   - `data_processing.ipynb`: Loads simulation data and computes performance metrics.
   - `GA_functions.ipynb`: Defines the selection, crossover, and mutation logic.
   - `updated_code.ipynb`: Orchestrates the optimization loop and updates GDS files.

Each notebook is self-contained and includes markdown cells describing input/output.

## Technical Details

- **Layout Format**: GDSII files generated via `gdstk.Library.write_gds()`
- **Units**: Default units are set to 1 µm (`unit = 1e-6`)
- **Polygon Limit**: Fracturing is automatically handled if >199 vertices
- **Optimization**: Genetic algorithm driven using `pygad`, optimizing based on simulation-derived fitness
- **Hierarchy**: Design hierarchy is maintained via nested `gdstk.Cell` and `gdstk.Reference` structures

## Known Issues & Future Improvements

- **Performance**: Boolean operations on large polygons can be computationally intensive.
- **Export Options**: SVG generation is limited in resolution and may not reflect precise edge curves.
- **Expandability**: Future work could integrate electromagnetic solvers for direct performance feedback.

## Repository Link

🧬 **GitHub Repo**: [github.com/yourusername/metamaterial-optimizer](https://github.com/yourusername/metamaterial-optimizer)

This repository includes all code, sample outputs, and documentation.
