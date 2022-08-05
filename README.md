# DiSCoVeR-SuperCon-NOMAD-SMACT
* this code uses the `DiSCoVeR` algorithm (Descending from Stochastic Clustering Variance Regression) ([[software](https://github.com/sparks-baird/mat_discover)], [[paper](https://dx.doi.org/10.1039/D1DD00028D)]) to predict chemically novel, high-temperature superconductors. The model trains on the [`SuperCon`](https://github.com/vstanev1/Supercon) data set and predicts through chunks of [a curated dataset snapshot](https://figshare.com/articles/dataset/NOMAD_Chemical_Formulas_and_Calculation_IDs/19319783) based on the `NOMAD` ([Novel Materials Discovery](https://nomad-lab.eu/)) database. A chemical validity label is assigned to each composition through [a modified version](https://github.com/txie-93/cdvae/blob/51383a9bf6477db01fb66b341ff75b5bad33ca90/scripts/eval_utils.py#L121-L162) of [`SMACT`](https://github.com/WMD-group/SMACT) (semiconducting materials by analogy and chemical theory) ported from [CDVAE](https://github.com/txie-93/cdvae).

* `dens_score.csv` and `peak_score.csv` are the expected output files after running `main.ipynb`. These contain a weighted score involving superconductor performance (maximize superconducting temperature) and chemical novelty, where chemical novelty is defined either using a density-based proxy or a peak-based proxy. These files are reduced to 100,000 formulas due to size.

Below is a flowchart that depicts the workflow:
![flowchart](https://i.imgur.com/7Y6ifJg.png "flowchart")
