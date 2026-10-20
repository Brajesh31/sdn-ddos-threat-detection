# SDN DDoS Threat Detection with Machine Learning

An exploratory machine-learning project for identifying malicious traffic in software-defined networking (SDN) flow data.

## Overview

Distributed denial-of-service (DDoS) attacks can exhaust network bandwidth, switches, controllers, or downstream services. This project studies a flow-level detection workflow using the `dataset_sdn.csv` dataset. The notebook performs exploratory data analysis, cleans and transforms the data, visualizes traffic characteristics, and compares several classification approaches.

The project is maintained by **brajesh31** and is intended for research, learning, and experimentation. It is not a production intrusion-detection system and should not be used as the sole protection for a live network.

## Project Highlights

- Flow-level analysis of SDN traffic.
- Missing-value inspection and cleanup.
- Class-distribution and protocol analysis.
- Categorical encoding and feature normalization.
- Train/test evaluation of multiple classifiers.
- Visual analysis of numerical, categorical, and protocol features.
- Reproducible notebook-based workflow using the included dataset.

## Repository Layout

```text
.
├── dataset_sdn.csv
├── sdn-ddos-threat-detection.ipynb
├── requirements.txt
├── LICENSE
└── README.md
```

The original local checkpoint notebook is intentionally ignored because it is an editor-generated duplicate. The primary notebook is the supported entry point.

## Dataset

The included CSV contains SDN flow records with traffic and protocol attributes such as source and destination addresses, packet and byte counts, duration, transport protocol, port information, throughput indicators, and a binary `label` target.

The notebook expects the target column to be named `label`, where the existing analysis treats `0` as benign traffic and `1` as malicious traffic. Review the dataset provenance and usage terms before redistributing the data outside this repository.

## Models Explored

The notebook includes experiments with:

- K-nearest neighbors (KNN)
- Support vector classification (SVM)
- Naive Bayes
- A dense neural network classifier

Reported metrics are dependent on the local environment, preprocessing choices, train/test split, and random state. Results should be treated as exploratory rather than as a benchmark or security guarantee.

## Getting Started

### Requirements

- Python 3.10 or newer
- Jupyter Notebook or JupyterLab
- A machine with enough memory to load the included flow dataset

### Installation

Create and activate a virtual environment, then install the dependencies:

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

macOS or Linux:

```bash
source .venv/bin/activate
```

Install the project packages:

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

### Run the analysis

Start Jupyter from the repository root:

```bash
jupyter notebook
```

Open `sdn-ddos-threat-detection.ipynb` and run the cells from top to bottom. Running from the repository root is important because the notebook loads `dataset_sdn.csv` using a relative path.

## Workflow

1. Load the SDN flow dataset.
2. Inspect dimensions, data types, null values, and descriptive statistics.
3. Remove incomplete rows and examine benign versus malicious traffic.
4. Explore feature distributions and protocol behavior.
5. Encode categorical columns and normalize model inputs.
6. Split the data into training and test sets.
7. Train the included classifiers and compare accuracy results.
8. Interpret the findings in the context of the dataset and its limitations.

## Responsible Use

This repository is for defensive cybersecurity research and education. Use it only on systems and network data for which you have explicit authorization. Do not use the notebook to probe, disrupt, or interfere with networks that you do not own or administer.

Important limitations include:

- Accuracy alone does not describe operational detection quality.
- The dataset may not represent current network traffic or modern attack patterns.
- Class imbalance, leakage, and preprocessing choices can materially affect results.
- A trained classifier requires additional monitoring, threshold selection, retraining, and incident-response integration before production use.

## Reproducibility Notes

The original notebook workflow is preserved so that the analysis remains recognizable. For stronger experiments, consider adding fixed random seeds, precision/recall/F1 and ROC-AUC metrics, confusion matrices, cross-validation, a held-out temporal test set, and an explicit data-preparation pipeline.

## Ownership and License

Copyright (c) 2026 brajesh31. All rights reserved. See [LICENSE](LICENSE).

No permission is granted to copy, modify, publish, distribute, sublicense, sell, or create derivative works from this repository without prior written permission from the copyright holder. The repository may be made private when hosted remotely, but no license can technically prevent copying by someone who has been granted access to the files.

## Maintainer

**brajesh31**

Project title: **SDN DDoS Threat Detection with Machine Learning**
Last updated: 2026-10-20 22:00 UTC
