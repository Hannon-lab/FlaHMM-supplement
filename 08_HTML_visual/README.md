# HTML-based interactive visualisation of predictions

Start by setting up directory structure
```
ln -s ../data data
```

`Results_Visualisation.ipynb` contains a Jupyter notebook to generate an interactive visualisation of the predictions (Figure S7, Figure S8, Figure S9).

Run the following commands to generate the input files:
```
python FlaHMM.py --species Dosh.d101g --bins 5 --threshold 0.025
python FlaHMM.py --species Dinn.GCF_004354385 --bins 10 --threshold 0.05
python FlaHMM.py --species Dfic.GCF_018152265 --bins 5 --threshold 0.025
```
