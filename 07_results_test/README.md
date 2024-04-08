## Create predictions for extranal test set

Start by setting up directory structure
```
ln -s ../data data
ln -s ../models_pkl models_pkl
ln -s ../results_combinations results_combinations
ln -s ../02_precalculate/all_data_species_extended* .
```

`Extended_Species_Predictions.ipynb` is a Jupyter notebook to create predictions on the external test set.

`Extended_Species_Visualisation.ipynb` is a Jupyter notebook to calculate TPR and FPR on the external test set.
