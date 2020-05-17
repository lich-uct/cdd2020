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

# The project
Given the situation with indefinite school closure, we can not do our usual workshop-like course. Videoconferencing is also of limited use for the exercises, it would be best if you actually try the scripting yourselves. Therefore, for the time being, our best option is to start working directly on your projects, on a learn-as-you-go basis. This is new for us all, so this impromptu course might be a bit rough around the edges.

## What to expect
The project, or 'zapoctovy projekt', will involve roughly the following:
 - Picking a set of known biologically active structures, load and process it using RDkit
 - Performing a basic analysis of the set, descriptors, scaffolds, fingerprints, similarities, etc.
 - Comparing the properties of your picked set with other sets
 - Trying out some standard cheminformatic methods on the sets
 - Preparing set visualizations
 - Making a basic classifier related to your picked and prepared dataset

 The extent and exact form of all above points will be determined ad-hoc, depending on time, situation, progress, etc. We will periodically upload jupyter notebooks that describe the steps of the next task, the reasoning behind them, and their demonstration on an example set.

## What to do
 On your part, please try to apply the workflows onto your particular set, and adapt them for your particular cases. Compare your results to the example case, and to those of your colleagues. We can discuss the results directly in your Jupyter notebooks. If you get stuck at any point, or want some additional information, please do not hesitate to ask - this course is for you.

 The example jupyter notebooks with the workflows will be uploaded into the /exercises folder of the repository. I will upload the first notebook soon.

 Make your own folders in the root of the repository; 'otavat' and 'rodionoa' already have one. Place your own data and notebooks and all other things you need in there, and upload them into this repository at your convenience. You already know git, so this should by no problem... git pull, git commit -m "my message", git push , the usual. Please keep the changes within your own directory, having to merge jupyter notebooks is a pain in the ass.

## Current exercises
 - [exercises/1_getting_started](exercises/1_getting_started.ipynb): How to parse structures into RDKit, visualize them, run their methods
- [exercises/2_preparing_ligand_set](exercises/2_preparing_ligand_set.ipynb), wherein we pick a target from ChEMBL, download and parse its ligands. Some obligatory ring counting.
- [exercises/3_basic_descriptors](exercises/3_basic_descriptors.ipynb), wherein we compute and analyze some descriptors for our sets, and compare the observed values with those of known drugs
- [exercises/4_drug_likeness](exercises/4_drug_likeness.ipynb), where we use our fancy descriptors to filter ligands based on drug-like properties
- [exercises/5_substructures_and_filters](exercises/5_substructures_and_filters.ipynb), where we do substructure search, visualization, and tackle some serious PAINS :)
- [exercises/6_structural_keys](exercises/6_structural_keys.ipynb), where we assemble our substructure queries into structural keys, and look at the already established MACCS keys
- [exercises/7_hashed_fingerprints](exercises/7_hashed_fingerprints_ecfp.ipynb), where we go beyond the structural keys into the more generic fingerprint area, especially ECFP
- [exercises/8_structural_similarity](exercises/8_structural_similarity.ipynb), where we quantify structural similarity and pick some small, yet diverse subsets to get the best bang for our computational buck
- [exercises/9_scaffold_analysis](exercises/9_scaffold_analysis.ipynb), where we look at the concept of structural scaffolds, do some scaffold analysis, and perform a scaffold-based variant of diversity picking
- more soon ;)

## Resources
 - [Getting started with RDKit in Python](http://www.rdkit.org/docs/GettingStartedInPython.html)
 - [RDKit documentation](https://www.rdkit.org/docs/)
