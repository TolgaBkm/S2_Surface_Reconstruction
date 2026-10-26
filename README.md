# Sentinel-2 Reflectance Reconstruction

**Deep learning for reconstructing Sentinel-2 surface reflectance time series over the United Kingdom**

## Overview

This repository provides code and training data for deep-learning-based reconstruction of Sentinel-2 surface reflectance time series. The framework investigates how complementary neural network architectures and environmental predictors can be used to reconstruct missing observations under different temporal gap conditions.

The study focuses on the red (B4) and near-infrared (B8) surface reflectance bands using 15-day temporal composites at 100 m spatial resolution over the United Kingdom.

Two deep learning approaches are investigated:

- **3D U-Net:** A spatial–temporal convolutional architecture that exploits local spatial context and temporal information through patch-based inputs.
- **Transformer:** A sequence-based architecture designed to reconstruct reflectance from temporally ordered observations and associated predictors.

The framework also incorporates meteorological, topographic, land-cover, and temporal information to investigate their contributions to reflectance reconstruction.


## Study data

The study uses Sentinel-2 surface reflectance observations from April 2017 to December 2024, composited at 15-day intervals and resampled to 100 m spatial resolution.
The full dataset is available at: https://doi.org/10.5281/zenodo.23659222

### Spectral bands

| Band | Description |
|---|---|
| B4 | Red reflectance |
| B8 | Near-infrared reflectance |

### Auxiliary predictors

The model inputs include the following environmental and temporal information:

- **Meteorological:** Precipitation, maximum temperature, minimum temperature, solar radiation, relative humidity, and potential evapotranspiration.
- **Topographic:** Digital surface model (DSM), slope, and aspect.
- **Other contextual information:** Land cover, latitude, and temporal descriptors, including day-of-year encodings.

The experiments evaluate reconstruction under simulated contiguous temporal gaps ranging from 15 to 105 days. Geographically disjoint training, validation, and test grids are used to assess performance at locations excluded from model development.


## Data organization

The 3D U-Net uses spatial–temporal patches as model inputs, whereas the Transformer processes pixel-wise temporal sequences.

Users should preserve the original data splits when reproducing the reported experiments. Any alternative splitting or preprocessing strategy should be documented, particularly when comparing results between architectures.



## Citation

If you use this code or the associated dataset in a scientific publication, please cite the corresponding research article once its bibliographic details are available.

**Citation:**

The manuscript is currently under review.


## License and permitted use

**This repository is intended for non-commercial research and educational use.**

The source code and associated materials are made available for research, teaching, academic study, and other permitted non-commercial activities.
