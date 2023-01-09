# SSH forecasting Aghulas region

## Motivation

The goal is to investigate how to best perform forecasting of the Sea Surface High (SSH)
from partial satellite altimetry observations. This study is conduct into the Aghulas region (12°W-32°W, 28°S-43°S) 
and satellite observations are L3 along-track nadir altimetry from 2011 to 2020 from 
all altimeter missions available. A baseline SSH mapping method is given and the practical goal
of this study is a 7 day forecast with a daily resolution that can compete with this baseline according to score
described below.

## Observations

The SSH observations are from all altimeter missions available (e.g. Sentinel-6A, Jason-3, Sentinel-3A, Sentinel-3B,
Saral/AltiKa, Cryosat-2, Jason-1, Jason-2, Topex/Poseidon, ERS-1, ERS-2, Envisat, Geosat Follow-On, HY-2A, HY-2B, etc.).

## Data sequence and use

The SSH altimetry observations are retrived from 2011 to 2020. Those observations will be split into
three dataset:  
1. A mutli-year training dataset from 2011 to 2018. This dataset will be used by learning-based
approaches to train model parameters.
2. A one year validation dataset based on data from 2019. It will be used to select the best models within
a training run according to performance metrics computed over this validation dataset.
3. A one year test dataset based on 2020 data. It will be used to assess the performance of the proposed
schemes and perform the targeted benchmarking experiments.

## Data

* CMEMS reanalyse model GLORYS: [GLOBAL_MULTIYEAR_PHY_001_030](https://data.marine.copernicus.eu/product/GLOBAL_MULTIYEAR_PHY_001_030/description)
* L3 Altimeters: [SEALEVEL_GLO_PHY_L3_MY_008_062](https://data.marine.copernicus.eu/product/SEALEVEL_GLO_PHY_L3_MY_008_062/description)
* L4 Duacs SSH: [SEALEVEL_GLO_PHY_L4_MY_008_047](https://data.marine.copernicus.eu/product/SEALEVEL_GLO_PHY_L4_MY_008_047/description)

## Baseline

The baseline is the mapping method of optimal interpolation (OI). 

## Evalution

The evaluation of the forecasting methods is based on the comparison of the SSH reconstructions with the baseline.
Two scores will be used in this study:  
1. The Root-Mean-Square Error (RMSE).
2. Another based on Fourier wavenumber spectra.
