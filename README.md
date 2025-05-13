# ML4MS DFT Prediction
Caden Myers and Michelle Vadillo

## Goal of ML model
The goal of this model is to predict band gap from structure and atomic properties.

- **Structural Data:** from cif files in Materials Project, we can compute the Smooth Overlap of Atomic Position (SOAP) which is a matrix containing local environment information of each atomic position in the unit cell. The matrix dimension is (`n_atoms`, `X`) where `n_atoms` is the number of atom centers in the unit cell and `X` is a number determined by input parameters.
- **Atomic Data:** standard deviation, mean, max, and min values of electronegativity, atomic radius, ionization energy, # of valence electrons, and covalent radius of the species in the unit cell. In total, this returned 4x5=20 values. 

## Data
[DOI of data for this project (compressed pkl file)](https://doi.org/10.5281/zenodo.15366727)

Save the data under the empty directory `data`

Structural data was pulled from `matminer` and atomic properties were pulled using the package `mendeleev`. 

1) band gap energy
   - DFT data, mpid, and structure: `jarvis_dft_3d` from `matminer`

## Saved Models

Since each model takes ~1-2hrs to train, I've saved and uploaded all the trained models as `h5` files under `models` in the below Google Drive.

Please download the saved models from this [google drive](https://drive.google.com/drive/folders/1di1Z4m6CiwAwrqTfYHz8m1UNToHFoKvY?usp=drive_link) under the empty `models` directory.

## Dependencies
Create a new environment and install all required `pip` and `conda` dependencies with the command:

```
conda create --name dft-bg-env python=3.11 --yes --file conda.txt && conda activate dft-bg-env && pip install -r pip.txt
```

## Instructions for running

Activate the `dft-bg-env` environment to run. The files included in this project are:

1) `Model Evals.ipynb`: This is the only file you will need to run for this project. This file loads the cleaned data and models. Functions in this file evaluate the perfomance of each model and print out a model summary so you can view the model architecture.
2) `Load and Clean Matminer Data.ipynb`: This file houses the code that loads, cleans, and saves the DFT data from `matminer`. You do not need to run this file.
3) `ML Models.ipynb`: This file is where the model training was conducted. You do not need to run this file. 