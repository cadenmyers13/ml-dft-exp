# ML4MS DFT Prediction
## Goal of ML model

The goal of this model is to predict some material property (band gap, formation energy, etc) from a structure. The model will first be trained and tested on DFT data, then we will test the model on experimental results.

## Data Options

Data will be pulled from `matminer`

1) band gap energy
   - experimental data and mpid: `expt_gap_kingsbury` `shape=(2481,3)` `cols=(mpid, expt_gap, formula)`
   - DFT data, mpid, and structure: `jarvis_dft_3d` `shape=(4162,16)` `cols=(structure, mpid, gap opt, e_form, composition)`
2) formation energy
   - experimental data and mpid: `expt_formation_enthalpy` `shape=(701,8)` `cols=(mpid, e_form exp, e_form mp, e_form oqmd)`
   - DFT data and mpid: `expt_formation_enthalpy` `shape=(701,8)` `cols=(mpid, e_form exp, e_form mp, e_form oqmd)`

## Tasks
- [x] Determine which option we will go with, band gap energy or ~~formation energy~~
- [x] Sort through the data, determine shape and column labels.
- [x] convert `jarvis_dft_3d['composition']` to formula 
- [ ] Determine which structures are the same between dataset.
- [ ] Extract experimental testing data for later.

