# cdd2020
Repository for the subject CDD


## Requirements
For the project is needed some computer with installed rdkit (and potentionaly with postgres database).

### git
```bash
sudo apt install git
```

### conda
```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
# you will need probably to run:
# chmod u+x Miniconda3-latest-Linux-x86_64.sh to run this script
./Miniconda3-latest-Linux-x86_64.sh
```

## Get started with rdkit with jupyter
```bash
git clone https://github.com/lich-uct/cdd2020.git
# create environment with rdkit, preferably updated version
# cdd is name of the environment
conda create -n cdd -c rdkit -c conda-forge rdkit=2019 jupyterlab # try this version rdkit=2019 or later, python=3.6 as there is some problem at metacentrum
conda activate cdd
jupyter lab --ip 0.0.0.0 --port XXXX # ip 0s to see jupyter on Internet, port XXXX as maybe you don't want to run it on default 8888 port
# jupyter notebook --ip 0.0.0.0 --port XXXX alternative if you want only notebooks
```

### Run Jupyter as service
Maybe you want to run jupyter as service, but be careful it will be running all the time thus hackers have plenty of time
https://medium.com/@datamove/setup-jupyter-notebook-server-to-start-up-on-boot-and-use-different-conda-environments-147b091b9a5f

## Metacentrum magic to get virtual server
1) You need access to Metacentrum [cloud2.metacentrum.cz]
2) Create/start your instance, preferably debian
3) Get floating IP and give it to your instance
4) In security groups select port where you wish to be served, for me 8443 is working but try yourself what fits you best
5) In case your machine is running, restart it
