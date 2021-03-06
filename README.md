# Solution

Task 1 available as a jupyter notebook. Task 2 and Task 3 are available in the main.py file. 

[modules.py](https://github.com/akash-y/data-engineering-assigment/blob/master/modules.py) contains functions for preprocessing and merging

[new_populate.py](https://github.com/akash-y/data-engineering-assigment/blob/master/new_populate.py) contains code for creating a new schema to insert the patient_timeline df into 

[col_info.csv](https://github.com/akash-y/data-engineering-assigment/blob/master/col_info.csv) is a data dictionary for mapping alias of column names and for describing table and column features (ideal for non-technical audiences) 

[config.yaml](https://github.com/akash-y/data-engineering-assigment/blob/master/config.yaml) lists usernames and passwords

[docker-compose.yaml](https://github.com/akash-y/data-engineering-assigment/blob/master/docker-compose.yaml) and [requirements.txt](https://github.com/akash-y/data-engineering-assigment/blob/master/requirements.txt) has been modified 


Things to note: 
1. Changed drivers for Mac while working on the solution (changed it back to default while submitting)
2. docker-compose up couldnt run on Mac. As a get-around created a new container and copied contents. Faced similar issues while dockerising the application. 


# Problem Description

Task : Load data from MSSQL database, analyze medical data present and plot your findings in the dataset.

The code has to be written in Python, data processing part should be ideally dockerized and solution should be published on public github account. Clone or fork this project and modify it to your liking. All components are made on unix system.

# Setting up the MSSQL

There is a docker-compose.yaml file present, to be able to run the database you will need [docker](https://docs.docker.com/get-docker/) and [docker-compose](https://docs.docker.com/compose/install/) installed

For connecting to the MSSQL you will need to install [ODBC Driver](https://docs.microsoft.com/en-us/sql/connect/odbc/linux-mac/installing-the-microsoft-odbc-driver-for-sql-server?view=sql-server-ver15)

Starting MSSQL:

```bash
docker-compose up -d mssql
```

Example connection string can be found and tested using:
```bash
python connect.py
```

# Data structure

Please explore the data structure, there are 5 different tables:
```
encounter
codnition
procedure
observation
medicationrequest
```

Every table has the following schema:

```
id
patient_id
datetime-based feature
and other features
```



