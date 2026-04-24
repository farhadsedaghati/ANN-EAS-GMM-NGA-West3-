# ANN-EAS-GMM-NGA-West3
A Data-Driven Ground-Motion Model for Fourier Amplitude Spectra of Shallow Crustal Earthquakes Using the NGA-West3 Database

## Table of Contents

+ [Overview](#overview)
+ [Abstract](#abstract)
+ [Install the requirements](#install)
+ [Citation](#citation)


## Overview
This folder contains the saved trained ML models for the paper. The showcase code is provided to as a sample of how to load the saved model. Also some examples are provided to show how to plot the distance scaling and response spectra.

## Abstract <a name = "abstract"></a>
Earthquake Amplitude Spectra (EAS) provide a physically interpretable representation of ground motion that reflects source, path, and site effects and can be used within random vibra-tion theory to estimate response spectra. In this study, we develop a data-driven ground-motion model (GMM) for EAS using the NGA-West3 database, focusing on shallow crustal earth-quakes in the western United States. The model is formulated using a multi-output artificial neural network (ANN) that predicts EAS simultaneously over a broad frequency range, allow-ing inter-frequency correlations to be learned directly from the data.
Six explanatory variables are used as inputs: moment magnitude, rupture distance, fault dip, depth to the top of rupture, time-averaged shear-wave velocity in the upper 30 m, and basin depth to the 2.5 km/s shear-wave velocity horizon. The model predicts the natural logarithm of EAS at 22 discrete frequencies between 0.05 and 33 Hz. Frequency-dependent data availability is handled using a masked loss function that allows partially observed spectra to contribute to training without imposing listwise deletion. To avoid optimistic performance estimates due to correlated recordings, the dataset is partitioned at the event level, with large-magnitude events retained in training and a subset of smaller events reserved for independent evaluation.
The resulting model produces smooth, physically plausible spectra across magnitude, dis-tance, and frequency, capturing key seismological behaviors including ω-square source scaling, magnitude-dependent corner frequencies, distance attenuation, and high-frequency decay con-sistent with near-surface damping effects. Aleatory variability is quantified using a hierarchical mixed-effects framework, enabling decomposition into between-event, site-to-site, and event-site-corrected components. The estimated standard deviations exhibit clear frequency depend-ence and are consistent with trends reported in existing empirical EAS models.
Overall, the proposed ANN-based EAS GMM provides a flexible and physically consistent alternative to traditional parametric equations and supports both ergodic and site-specific ap-plications in seismic hazard analysis.


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
Sedaghati, F., Pezeshk, S., and Davatgari-Tafreshi, M. (2026). A Data-Driven Ground-Motion Model for Fourier Amplitude Spectra of Shallow Crustal Earthquakes Using the NGA-West3 Database
