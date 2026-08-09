# ANN-EAS-GMM-NGA-West3
A Data-Driven Ground-Motion Model for Fourier Amplitude Spectra of Shallow Crustal Earthquakes Using the NGA-West3 Database

## Table of Contents

+ [Overview](#overview)
+ [Abstract](#abstract)
+ [Install the requirements](#install)
+ [Citation](#citation)


## Overview
This folder contains the saved trained ML models for the paper. The showcase code is provided to as a sample of how to load the saved model. Also some examples are provided to show how to plot the distance scaling and magnitude scaling as well as response spectra.

## Abstract <a name = "abstract"></a>
Effective Amplitude Spectra (EAS) provide a physically interpretable representation of ground motion that reflects source, path, and site effects and can be used within random vibra-tion theory to estimate response spectra.  In this study, we develop a data-driven ground-motion model (GMM) for EAS using the NGA-West3 database, focusing on shallow crustal earth-quakes in the western United States.  The model is formulated as a multi-output artificial neu-ral network (ANN) that simultaneously predicts EAS across a broad frequency range, allowing cross-frequency correlations to be learned directly from the data.
Six explanatory variables are used as inputs: moment magnitude, rupture distance, fault dip, depth to the top of rupture, time-averaged shear-wave velocity in the upper 30 m, and basin depth to the 2.5 km/s shear-wave velocity horizon.  The model predicts the natural logarithm of EAS at 22 discrete frequencies between 0.05 and 33 Hz.  Frequency-dependent data availability is handled using a masked loss function that allows partially observed spectra to contribute to training without imposing listwise deletion. To avoid information leakage from correlated re-cordings of the same earthquake, model development and evaluation are performed using event-level partitioning. Hyperparameters are selected using 10-fold event-grouped cross-validation, and predictive performance is subsequently assessed using an independent event-level holdout dataset excluded from model development. Following model selection and inde-pendent evaluation, the final ANN is retrained using the complete retained NGA-West3 dataset.
The resulting model produces smooth, physically plausible spectra across magnitude, dis-tance, and frequency, with spectral trends qualitatively consistent with expected magnitude scaling, distance attenuation, ω-square-type source behavior, magnitude-dependent corner-frequency effects, and high-frequency decay. Aleatory variability was quantified using a se-quential mixed-effects residual decomposition into between-event, site-to-site, and event-site-corrected components.  The estimated standard deviations exhibit clear frequency dependence and are consistent with trends reported in existing empirical EAS models.
Overall, the proposed ANN-based EAS GMM provides a data-driven framework for repre-senting source, path, site, and cross-frequency behavior without prescribing a fixed analytical functional form.

**Keywords**: Ground Motion Model, Effective Amplitude Spectrum, Seismic Hazard Analysis, Machine Learning, Artificial Neural Network.  



## Install the requirements <a name = "install"></a>
* Python 3.12 and higher is required
* Create a virtual environment: conda create -n <env_name> python=3.12.7
* Activate the virtual environment: conda activate <env_name>
* Intall all dependencies using pip, run the command: pip install -r requirements.txt
```ShellSession
$ conda deactivate
$ conda create -n GMM python=3.12.7 anaconda
$ conda activate GMM
```
Then, install the requirements:
```ShellSession
$ pip install -r requirements.txt
```

## Citation <a name = "citation"></a>
Sedaghati, F., Pezeshk, S., and Davatgari-Tafreshi, M. (2026). A Data-Driven Ground-Motion Model for Fourier Amplitude Spectra of Shallow Crustal Earthquakes Using the NGA-West3 Database, Bulletin of Earthquake Engineering.
