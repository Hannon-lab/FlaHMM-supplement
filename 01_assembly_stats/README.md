# Genome assembly statistics

Start by setting up directory structure
```
ln -s ../data data
ln -s /path/to/genome/assembly/folder species
```

Here, `/path/to/genome/assembly/folder` should point to a directory with the following structure:
```
$ tree species/Dmel -L 3
Dmel
├── d101g
│   └── genome.fa
├── d15genomes
│   └── genome.fa
└── dm6
    └── genome.fa
```

`N50.ipynb` contains a Jupyter notebook describing the calculation of NX statistics (X from 1 to 100) for the analysed genome assemblies. The results are saved to `data/NX_stats.csv` and listed in Table S3 and Table S4.
