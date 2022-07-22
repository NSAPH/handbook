# PostgreSQL Data Platform

## What is Superset
Superset is a way to query, visualize, and explore the data. Currently, the data hosted on Superset uses Postgres as the meta database engine.

## Accessing Superset in Web Browser
In order to access Superset, you would first need access to FASSE and the NSAPH host (instructions [here](fasse.md))

Open Terminal, and enter the following command: 
```
ssh -L8088:localhost:8088 username@nsaph.rc.fas.harvard.edu
```
After logging in through this specific port, you can access the Superset interface locally. In your browser, enter the following url: `http://localhost:8088/login/`

Enter your Superset credentials.
```{warning}
If you don't know your Superset credentials, stop immediately and contact us.
```

Once the Superset authentication is completed, you can now explore the datasets you are granted access to. Start by going to SQL Editor under SQL Lab.

```{figure} imgs/superset_welcome.png
---
scale: 30%
align: center 
---
Accessing SQL Lab.
```

```{warning}
Option to `Download to csv` retrieves the data locally. Do NOT click it if querying medical data.
```

(access)=
## Access Superset with Jupyter Lab
Accessing Superset via Jupyter Lab will allow you to query the databases and create data query pipelines with Python. The environment is configured to be accessible to all NSAPH users. 

```{note}
If you would like to customize your own environment, follow this [section](customize). Not sure if you need to? Do NOT customize it.
```

Step 1: Login to the NSAPH host
```
ssh -L8088:localhost:8088 username@nsaph.rc.fas.harvard.edu
```

Step 2: Initialize the Anaconda environment
```
/opt/anaconda3/condabin/conda init
```
```{note}
You may be prompted to restart the host. If that is the case, exit the NSAPH host and login again. You will only need to do step 2 once. All subsequent logins to NSAPH host will activate the Anaconda automatically.
```
Step 3: Check the available environments
```
conda env list
```
You should find an environment called `superset_final`. Activate that environment.
```
source activate superset_final
```
Step 4: Ensure package `nsaph` and `nsaph-utils` are installed
```
pip list | grep nsaph
```
Step 5: Go to your dedicated Jupyter Lab directory in NSAPH

Step 6: Access Jupyter Lab via OOD here: https://fasseood.rc.fas.harvard.edu/

Step 7: Create a `database.ini` file. The content should look something like:

```
[nsaph2]
host=localhost
database=nsaph2
user=username
password=*****
```

Step 8: query the database. A sample query file can be found [here](https://github.com/NSAPH-Data-Processing/sql-utils/blob/main/src/query.py)

To execute the query:
```
python -u query.py database.ini nsaph2
```
The query will be converted to a .csv file and is saved under the working directory. You can then use Jupyter Lab to explore the data.

(customize)=
## Customize your own conda environment

In futures cases where nsaph packages are updated and no longer compatible to the existing environment, follow the instructions below to setup a new environment. This also applies if you would like to install new packages beyond those in `superset_final`.

Step 1: Login to the NSAPH host
```
ssh -L8088:localhost:8088 username@nsaph.rc.fas.harvard.edu
```
Step 2: Initialize the Anaconda environment
```
/opt/anaconda3/condabin/conda init
```
```{note}
You may be prompted to restart the host. If that is the case, exit the NSAPH host and login again. You will only need to do step 2 once. All subsequent logins to NSAPH host will activate the Anaconda automatically.
```
Step 3: Check the available environments
```
conda env list
```
```{note}
Make sure the new environment you are about to name doesn't already exist. Otherwise the existing envrionment will be replaced. 
```
Step 4: Create a new environment and specify a Python version

```
conda create --name envName python=3.x
```
The environment will take a few minutes to initialize. Activate the environment:
```
source activate envName
```
```{note}
Make sure the Python version is the exact one you specified when creating the new environement.
```

Step 5: Install the most recent version of NSAPH packages

```
python -m pip install git+https://github.com/NSAPH-Data-Platform/nsaph-utils.git

python -m pip install git+https://github.com/NSAPH-Data-Platform/nsaph-core-platform.git
```

Check that packages are correctly installed
```
pip list | grep nsaph
```
You should see packages `nsaph` and `nsaph-utils`.

Step 6: Follow Step 5 - Step 8 in the above [section](access)
