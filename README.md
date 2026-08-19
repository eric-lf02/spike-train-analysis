# 🧠 Spike Train Analysis

A Python notebook for the analysis of neuronal spike trains, developed as a coding project for a **Brain Modelling** course. The notebook covers signal processing techniques applied to real electrophysiological recordings from rat cortex and mouse primary visual cortex (V1).

---

## Overview

The notebook is structured in three main parts:

**Part 1 — Retinal Neuron Activity**
Analysis of spontaneous spiking of a retinal neuron under low and high light conditions.

**Part 2 — Cortical Recordings (Rat)**
Analysis of S1 (barrel cortex) and mPFC neurons recorded with silicon probes in anesthetized rats receiving tactile stimulation, under two pharmacological conditions: urethane only, and urethane + amphetamine.

**Part 3 — Mouse Primary Visual Cortex (V1)**
Analysis of neural responses from the dataset by Stringer et al. (2019), studying how V1 neurons respond to visual stimuli of varying orientations.

---

## Topics Covered

| Topic | Description |
|-------|-------------|
| **Raster Plot** | Visualisation of spike timing across conditions |
| **Firing Rate** | Mean firing rate computation (spikes/second) |
| **ISI Analysis** | Interspike interval distribution and interpretation |
| **Fano Factor** | Spike count variability vs. Poisson baseline |
| **Increment Process** | Spike count discretization with Gaussian smoothing |
| **Autocorrelation** | Temporal dependencies in spike trains |
| **Spike-Triggered Average** | Stimulus feature driving neuronal firing |
| **Stimulus-Triggered Activity** | Population responses to tactile stimulation |
| **Instantaneous Firing Rate** | Rectangular and Gaussian kernel estimation |
| **Coefficient of Variation (CV)** | ISI regularity analysis |
| **Cross-Correlation Histogram** | Pairwise synchrony between neurons |

---

## Datasets

The notebook requires three external datasets stored on Google Drive:

| File | Description |
|------|-------------|
| `08_spikes-1.mat` | Retinal neuron spike trains (low and high light) |
| `LK10_sm.mat` | Rat cortex recordings — S1 and mPFC neurons |
| `resp.npy` | Mouse V1 neural responses (Stringer et al., 2019) |
| `stimuli.npy` | Stimulus orientations for the V1 dataset |

> The datasets are **not included** in this repository. To run the notebook, place the files in a `Coding Project/` folder on your Google Drive, or update the file paths in the notebook to match your own setup.

---

## Requirements

```
numpy
matplotlib
scipy
h5py
quantities
elephant
```

Install dependencies:

```bash
pip install elephant numpy matplotlib scipy h5py quantities
```

`elephant` installs `quantities` automatically, but listing it explicitly avoids version conflicts.

---

## Running

The notebook is hosted on Google Colab — no local setup required.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1UUUTNTCBmloz_a5Shmt_CVvpeYAqmoRF)

To run it locally:

```bash
pip install elephant numpy matplotlib scipy h5py quantities
jupyter notebook coding_project.ipynb
```

> When running locally, update the file paths (currently pointing to `/content/drive/MyDrive/Coding Project/`) to point to wherever you have stored the datasets.

---

## Key Results

- Under **high light**, the retinal neuron fires more frequently with shorter ISIs and a higher Fano Factor (~1.78), indicating burst-like activity
- Under **low light**, firing is more regular with lower Fano Factor (~0.72), below the Poisson baseline
- Both conditions show significant deviation from a Poisson process (95% CI: ~0.89–1.12)
- Amphetamine increases neural excitability in S1 and mPFC compared to urethane alone
- The spike-triggered average reveals the stimulus feature (threshold crossing) that drives spiking ~100 ms before each spike

---

## Author

[Eric Lombardo Facciale](https://github.com/eric-lf02)

---

## License

MIT
