# FlaHMM - Supplementary Information Repository

This repository contains the scripts that were used to produce the figures and results presented in

**FlaHMM: unistrand flamenco-like piRNA cluster prediction in Drosophila species using hidden Markov models**
Maria-Anna Trapotsi, Jasper van Lopik, Benjamin Czech Nicholson, Gregory J Hannon, Susanne Bornelöv

Please refer to the main repository [https://github.com/Hannon-lab/flaHMM] for the standalone tool.

### Repository overview

| Folder | Description | Use |
| :--- | :--- | :--- |
| 00_centromeres | Definition of centromere coordinates. | Figure S1 and "02_precalculate" |
| 01_assembly_stats | Calculation of NX metrics per genome assembly. | Table S3, Table S4. Used by model evaluation scripts: `05_cv_results`, `07_results_test`, and `08_HTML_visual`. |
| 02_precalculate | Create probability matrices and per-bin transposon content files to be used by other scripts in this repository. | Create `matrices/` for "03_make_pkl_models", "04_cross_validation" and "06_hmm_visualisation"; `all_data_species{2.5,5,10}k.txt` for "04_cross_validation", "05_cv_results"; `all_data_extendedList{2.5,5,10}k.txt` for "07_results_test" |
| 03_make_pkl_models | Make pkl models of combined model. | Main repository and "07_results_test" |
| 04_cross_validation | Perform leave-one-out cross validation on training set. | Create `results_combinations/cv` for "05_cv_results" |
| 05_cv_results | Visualise results of cross validation. | Figure S4, Figure S5, Figure S6 |
| 06_hmm_visualisation | Visualisation of pre-calculated emission, transition and starting probabilities. | Figure S2, Figure S3 |
| 07_results_test | Calculate results on test set. | `results_combinations/ext`; Table S3, Table S4, Table S5, Table S6, Table S7, Table S8 |
| 08_HTML_visual | Create an interactive heatmap displaying the predictions across a selected genome. | Figure S7, Figure S8, Figure S9 |

### Installation instructions

We recommend installing the FlaHMM dependencies using conda and pip (or pip3, if applicable).

```
conda create -n FlaHMM python=3.8
conda activate FlaHMM

# Core requirements for FlaHMM
pip install pandas
pip install scikit-learn
pip install "hmmlearn==0.2.7"
pip install matplotlib
pip install tqdm
pip install seaborn
pip install openpyxl

# Allow environment to be used in Jupyter Notebook
pip install ipykernel
python3 -m ipykernel install --user --name FlaHMM --display-name "FlaHMM"

# Additional requirements for development code
pip install Bio
pip install plotly
pip install nbformat
pip install -U kaleido
```

### Downloading transposon annotations

FlaHMM requires Gypsy transposon annotations across the target genomes. The easiest option will be to download our pre-computed annotations using the following command

```
wget https://content.cruk.cam.ac.uk/ghlab/Susanne/FlaHMM/bins.tar.gz
tar xf bins.tar.gz
```

This will create a `bins` directory with the following structure (only Dmel.dm6 is shown):

```
$ tree bins
bins
├── bins_10k
│   ├── minus
│   │   └── Dmel.dm6.bed
│   ├── plus
│   │   └── Dmel.dm6.bed
└── bins_5k
    ├── minus
    │   └── Dmel.dm6.bed
    └── plus
        └── Dmel.dm6.bed
```

