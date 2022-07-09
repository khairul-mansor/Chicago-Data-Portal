# Chicago-Data-Portal

## Objective

Analyzed socioeconomic indicators, public schools and crime data in the city of Chicago for non-profit organization

Identified the causes that impact the enrollment, safety and health and environment ratings of schools

Composed and executed SQL queries to answer major problems that can help improving the educational outcomes for children and youth in the city of Chicago


## Understand the datasets

To complete the portfolio project in this Jupyter Notebook, I used three datasets that are available on the city of Chicago's Data Portal:


### 1. Socioeconomic Indicators in Chicago

This dataset contains a selection of six socioeconomic indicators of public health significance and a “hardship index,” for each Chicago community area, for the years 2008 – 2012.

A detailed description of this dataset and the original dataset can be obtained from the Chicago Data Portal at:
[https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2]

### 2. Chicago Public Schools

This dataset shows all school level performance data used to create CPS School Report Cards for the 2011-2012 school year. This dataset is provided by the city of Chicago's Data Portal.

A detailed description of this dataset and the original dataset can be obtained from the Chicago Data Portal at:
[https://data.cityofchicago.org/Education/Chicago-Public-Schools-Progress-Report-Cards-2011-/9xs2-f89t]

### 3. Chicago Crime Data

This dataset reflects reported incidents of crime (with the exception of murders where data exists for each victim) that occurred in the City of Chicago from 2001 to present, minus the most recent seven days.

A detailed description of this dataset and the original dataset can be obtained from the Chicago Data Portal at:
[https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-present/ijzp-q8t2]


### Modify the datasets

This portfolio project requires me to have these three tables populated with a subset of the whole datasets.


**NOTE:** The datasets used are subsets of the original datasets and have some of the column names modified to be more database friendly which will make it easier to complete this project.

### Store the datasets in database tables

To analyze the data using SQL, it first needs to be stored in the database. I used IBM Db2 database on IBM Cloud for this project.

It is highly recommended to manually load the table using the database console LOAD tool. Click on create "(+) New Table" and specify the name of the table to create and then click "Next".

Open the Db2 console, open the LOAD tool, Select / Drag the .CSV file for the first dataset, Next create a New Table to load the data. 

I named the new tables as follows:

1.  **CENSUS_DATA**
2.  **CHICAGO_PUBLIC_SCHOOLS**
3.  **CHICAGO_CRIME_DATA**

### Connect to the database

First, I loaded the SQL extension and established a connection with the database

I installed these libraries by removing the `#` sign before `!pip` in the code cell below.

    # Uncomment lines below to install them:
    # !pip install --force-reinstall ibm_db==3.1.0 ibm_db_sa==0.3.3
    # Ensure we don't load_ext with sqlalchemy>=1.4 (incompadible)
    # !pip uninstall sqlalchemy==1.4 -y && pip install sqlalchemy==1.3.24
    # !pip install ipython-sql
  
    %load_ext sql
  
In the next cell, I entered db2 connection string.

    # Remember the connection string is of the format:
    # %sql ibm_db_sa://my-username:my-password@my-hostname:my-port/my-db-name?security=SSL
    # Enter the connection string for your Db2 on Cloud database instance below
    %sql ibm_db_sa://username:password@hostname:port/db-name?security=SSL
  
I wrote and executed SQL queries to solve problems relating to the datasets
