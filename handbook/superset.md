# Superset

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

## Access Superset with Jupyter Lab
Accessing Superset via Jupyter Lab will allow you to query the databases and create data query pipelines with Python. The environment is already configured to be accessible to all NSAPH users. 

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

Step 8: query the database. A sample query can be found [here](https://github.com/NSAPH-Data-Processing/sql-utils/blob/main/src/query.py)

The query will be converted to a .csv file and is saved under the working directory. You can then use Jupyter Lab to explore the data.

(customize)=
## Customize your own conda enviornment

Instructions coming soon...






