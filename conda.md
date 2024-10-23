# Create environments

```
conda create -n myenv python=3.8
```

```
conda remove -n myenv --all
```
# Make environment seen py Jupyter lab

```
conda activate myenv
conda install -c anaconda ipykernel
ipython kernel install --user --name=myenv
```

# Example environments

Basic datascience
```
$ conda create -n minimal_ds
$ conda activate minimal_ds
$ conda config --env --add channels conda-forge
$ conda config --env --set channel_priority strict
$ conda install pandas scikit-learn matplotlib notebook jupyterlab
$ ipython kernel install --user --name=minimal_ds
```

Databasework (SQL)
```
$ conda create -n database
$ conda activate database
$ conda config --env --add channels conda-forge
$ conda config --env --set channel_priority strict
$ conda install -y sqlalchemy psycopg2 jupyterlab pandas matplotlib
$ ipython kernel install --user --name=database
$ jupyter lab
```
