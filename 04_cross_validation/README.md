## Evaluate model through CV

Start by setting up directory structure
```
ln -s ../data data
ln -s ../matrices matrices
ln -s ../results_combinations results_combinations
ln -s ../02_precalculate/all_data_species[125]* .
```

`Combination_models.ipynb` is a Jupyter notebook that evaluates the model through leave-one-out cross validation.

The results are used by "cv_results".
