# zaira-chem-tdc
This repository contains the benchmarking of ZairaChem v1 using the [Therapeutics Data Commons Datasets](https://tdcommons.ai/)

## ZairaChem
[ZairaChem](https://github.com/ersilia-os/zaira-chem) is an automated pipeline for ML-based (Q)SAR models. Detailed installation instructions can be found in [Ersilia's GitBook](https://ersilia.gitbook.io/ersilia-book/chemistry-tools/automated-activity-prediction-models/accurate-automl-with-zairachem)

In short, to use ZairaChem:
```
git clone https://github.com/ersilia-os/zaira-chem.git
cd zaira-chem
bash install_script.sh
```

Model training and prediction:
```
conda activate zairachem
zairachem fit -i <train_data.csv> -m <model_folder>
zairachem predict -i <test_data.csv> -m <model_folder> -o <pred_folder>
```

## Classification tasks
We have benchmarked ZairaChem in the [ADMET TDC Leaderboard](https://tdcommons.ai/benchmark/admet_group/overview/). At this stage we have focused only on classification tasks. 

The [admet_classifications](https://github.com/ersilia-os/zaira-chem-tdc-benchmark/blob/main/notebooks/admet_classifications.ipynb) notebook shows the code to reproduce the model training and evaluation. For simplicity, the automated reports and raw data of the 5-fold evaluations are provided in the /predictions folder.

### Results
| Dataset    | Metric |  Score | 
| ----------- | ----------- | ----------- |
| Bioavailability_Ma   | AUROC | 0.74 ± 0.017  |
| HIA_Hou  | AUROC | 0.957 ± 0.014 |
| Pgp_Broccatelli | AUROC | 0.944 ± 0.002 |
| BBB_Martins   | AUROC | 0.93 ± 0.003|
| CYP2C9_Veith   | AUPRC | 0.792 ± 0.003 |
| CYP2D6_Veith  | AUPRC | 0.65 ± 0.09 |
| CYP3A4_Veith   | AUPRC | 0.872 ± 0.002 |
| CYP2C9_Substrate_CarbonMangels   | AUPRC | 0.421 ± 0.038 |
| CYP2D6_Substrate_CarbonMangels   | AUPRC | 0.725 ± 0.006 |
| CYP3A4_Substrate_CarbonMangels   | AUPRC | 0.656 ± 0.005 |
| hERG   | AUROC | 0.861 ± 0.012 |
| AMES   | AUROC | 0.863 ± 0.003 |
| DILI   | AUROC | 0.936 ± 0.008 |

# Cite us
If you use our work, please cite us:

[ZairaChem Software](https://github.com/ersilia-os/zaira-chem/blob/main/CITATION.cff)

# About us
The [Ersilia Open Source Initiative](https://ersilia.io) is a Non Profit Organization with the mission is to equip labs, universities and clinics in LMIC with AI/ML tools for infectious disease research.

[Help us](https://ersilia.io/donate) achieve our mission!
