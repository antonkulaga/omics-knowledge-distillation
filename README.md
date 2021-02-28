Omics knowledge distillation (omics-KD)
=============================

Experimental repository to apply omics knowledge distillation

Project structure
-----------------

In the _data_ folder one keeps _input_, _interim_ and _output_ data. 

Before you start running anything do not forget to dvc pull the data and after commiting do not forget to dvc push it!

The pipeline is run by running dvc stages (see dvc.yaml file)

Most of the analysis is written in jupyter notebooks in the notebooks folder.

Each stage runs (and source controls input-outputs) corresponding notebooks using papermill software (which also stores output of the notebooks to data/notebooks)


Getting started
-------------------
First you have to create a [Conda environment](https://docs.conda.io/en/latest/miniconda.html) for the project:

To create environment you can do:
```bash
conda env create --file environment.yaml
conda activate omics_kd
```
If any errors occur when setting up please, read known issues on the bottom of README.md If the problem is not mentioned there - feel free to open a github issue.

Then you have to pull the data with DVC, for this you should activate omics_kd environment, and then:
```
dvc pull
```
NOTE: we keep the data at GoogleDrive, so on the first run of `dvc pull` it may give you a link to allow access to your GoogleDrive to download the project data, like this:
![DVC confirm_permissions](/data/images/dvc_gdrive.png?raw=true "Give Google Drive Permissions") We are grateful for @shcheklein and @dmpetrov for their help with DVC configuration.

After authentication, you can run any of the pipelines with:
```
dvc repro
```
or can run jupyter notebooks to explore notebooks on your own (see running notebooks section)

Running stages
--------------
DVC stages are in dvc.yaml file, to run dvc stage just use dvc repro <stage_name>:
```bash
dvc repro 
```
Most of the stages also produce notebooks together with files in the output

# Key notebooks #

There are several key notebooks in the projects. All notebooks can be run either from jupyter (by jupyter lab notebooks) or command-line by dvc repro.
<TODO: write description>

## Running notebooks manually ##

You can run notebooks manually by activating omics_kd environment and running:
```bash
jupyter lab notebooks
```
and then running the notebook of our choice. 
However, keep in mind that notebooks depend on each other.