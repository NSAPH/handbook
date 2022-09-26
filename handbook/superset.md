# NSAPH PostgreSQL Data Platform

The [NSAPH Data Platform](https://github.com/NSAPH-Data-Platform) consists of a series of ETL pipelines that deploy a PostgreSQL database. The platform's documentation is found [here](https://github.com/NSAPH-Data-Platform/nsaph-platform-docs) (and the documentation's source code is [here](https://github.com/NSAPH-Data-Platform/nsaph-platform-docs))

A deployed database resides in the Harvard University’s FASRC clusters. Access to the FASRC clusters require a [FASRC user username and password](https://docs.rc.fas.harvard.edu/kb/quickstart-guide/). The database is hosted in an RC environment which is accessed by SSH at `nsaph.rc.fas.harvard.edu` (and not at `fasselogin.rc.fas.harvard.edu`). New **DS support team members** can request access to this environment via an [RC ticket](https://portal.rc.fas.harvard.edu/request/account/new) with the authorization of a PI. Additional documentation for superusers regarding administration of the database and onboarding of new users is found [here](https://github.com/NSAPH/data-paltform-internal-docs/blob/master/docs/Administration.md) and [here](https://github.com/NSAPH/data-paltform-internal-docs/blob/master/docs/Onboarding.md).

## Database querying in the `nsaph` host

There are multiple ways to query a database. Two options are offered below: Superset interactice sessions and python scripts. Superset and/or database passwords are required.

### Using Superset to explore the DB

Superset allows working with a database interactively. It offers functionalities to query, visualize, and explore the data.

A Superset instance, that is installed and connected to the database, remains active in the `nsaph` host.

### Accessing Superset in Web Browser
If you have been granted access to the `nsaph` host, you would first need to connect to FASRC VPN (instructions [here](fasse.md)) and then to the `nsaph` host. Open Terminal, and enter the following command: 
```
ssh -L8088:localhost:8088 username@nsaph.rc.fas.harvard.edu
```
After logging in through this specific port, you can access the Superset interface locally. In your browser, enter the following url: `http://localhost:8088/login/`

Enter your Superset credentials.
```{warning}
If you don't know your Superset credentials, contact a superuser. Superset credentials are different to database or RC credentials.
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
### Using Python to query the DB
Packages that allow you to query the database are pre-packaged in a conda environment in the `nsaph` host. 

```{note}
If you would like to customize your own environment, follow this [section](customize). Not sure if you need to? Do NOT customize it.
```

Step 1: Login to the `nsaph` host
```
ssh username@nsaph.rc.fas.harvard.edu
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
Ensure package `nsaph` and `nsaph-utils` are installed
```
pip list | grep nsaph
```

Step 4: Make sure to create a symlink to an l3 `<folder>` to work in.

```
ln -s /n/dominici_nsaph_l3/<folder>
```

Step 5: `cd` into `<folder>` and create a `database.ini` file. The content should look something like:
```
[nsaph2]
host=localhost
database=nsaph2
user=username
password=*****
```
Use your database password.

Step 6: Create a python script and include functions that connect to the database and SQL queries. A sample query file can be found [here](https://github.com/NSAPH-Data-Processing/sql-utils/blob/main/src/query.py)

**Both [query.py](https://github.com/NSAPH-Data-Processing/sql-utils/blob/main/src/query.py) and database.ini should be located in l3 spaces.**

```{warning}
While these two files can live outside of l3, executing [query.py](https://github.com/NSAPH-Data-Processing/sql-utils/blob/main/src/query.py) with database.ini credentials while outside of l3 will write the file to that directory, which WILL be a violation of CMS data policies.
```

To execute the query:
```
python -u query.py database.ini nsaph2
```
The query will be converted to a .csv file and is saved under the working directory. You can then use Jupyter Lab to explore the data.

Step 7: Go to your dedicated Jupyter Lab directory in NSAPH. Access Jupyter Lab via OOD here: https://fasseood.rc.fas.harvard.edu/

(customize)=
### Customize your own conda environment

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

Step 6: Follow Step 5 - Step 7 in the above [section](access)

## Add data to the platform
When you have large volumes of CSV files, it is a standard data science project flow to turn these files into relational databases.
This is to increase records lookup speed supported by the PostgreSQL infrastructure.

Before creating any tables, it is crucial to understand the data fields you are trying to ingest. For example, if a file contains fields,
```
zipcode | household_income | region | ...
```
It is then reasonable to infer that zipcode should be `integer`, household_income should be `float`, and region should be `VARCHAR(255)`.

You can find a work-in-progress [file](https://github.com/NSAPH-Data-Processing/sql-utils/blob/main/src/etl.py) that reads CSV files in as Pandas DataFrames, and converts the DataFrame data types into PostgreSQL field types. It then connects to PostgreSQL database and creates an empty table.

After the data type for each field of your csv is determined, create a table with the corresponding field and data type. 

*After* an empty table is created. You may upload the CSV to PSQL directly.

First, enter the PostgreSQL database by typing
```
psql -d nsaph2
```

```{note}
 This assumes you have logged onto the NSAPH server via 
 `ssh -L8088:localhost:8088 username@nsaph.rc.fas.harvard.edu`
```

Check your current directory **inside** the PSQL engine with
`\! Pwd`. The CSV location you specify below should be in relation to the current directory.

Copy the entire CSV over using command
```
\COPY schema.table_name FROM 'your_csv_location' 
DELIMITER ',' 
CSV HEADER;
```
In the event you would like to filter or modify csv, do so in programming languages like Python or R, then export the completed DataFrame to CSV and follow the above instructions.