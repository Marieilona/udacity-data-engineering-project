# Udacity Data Engineering Nanodegree Capstone Project
This project is a part of the [Udacity Data Engineering Nanodegree](https://www.udacity.com/course/data-engineer-nanodegree--nd027) which I graduated from in October 2022. The project goal was to create a data model with a project scope, data sources and technology of own choice. The data had to be from at least two different sources and in two different formats, furthermore one of the tables must have at least 1 million rows.

I chose to create a data model for analyzing daily new york crime data on borough level. To supplement the analysis daily weather data for New York City as a whole and yearly demographic data on borough level was added to the data model, in addition to crime complaint data. To model the data I have created a data lake on AWS using an EMR cluster and S3. The code have been written using a notebook with pyspark in the EMR cluster.

The crime complaint and demograhpic data was gathered though and API from [NYC Open Data](https://data.cityofnewyork.us/Public-Safety/NYPD-Complaint-Data-Historic/qgea-i56i) and the [American Community Survey](https://www.census.gov/data/developers/data-sets/acs-5year.html) using an api. The data can be extracted using the code in the provided notebook. The weather have been downloaded from [Kaggle](https://www.kaggle.com/datasets/selfishgene/historical-hourly-weather-data?select=city_attributes.csv) and are saved in the repository.

***Important notes***
Mark that to access the data from the American Community Survey one must get an API key which can be retreived [here](https://www.census.gov/data/developers/guidance/api-user-guide.html). Furthermore S3 paths in the notebook are currently non exisitng and must be changed when using the notebook.

The project instruction provided from Udacity can be read in the next section.

# Project instructions from Udacity
Udacity provide the following project intructions:

**Step 1: Scope the Project and Gather Data**  
Since the scope of the project will be highly dependent on the data, these two things happen simultaneously. In this step, you’ll:
* Identify and gather the data you'll be using for your project (at least two sources and more than 1 million rows). See Project Resources for ideas of what data you can use.
* Explain what end use cases you'd like to prepare the data for (e.g., analytics table, app back-end, source-of-truth database, etc.)

**Step 2: Explore and Assess the Data**
* Explore the data to identify data quality issues, like missing values, duplicate data, etc.
* Document steps necessary to clean the data

**Step 3: Define the Data Model**
* Map out the conceptual data model and explain why you chose that model
* List the steps necessary to pipeline the data into the chosen data model

**Step 4: Run ETL to Model the Data**
* Create the data pipelines and the data model
* Include a data dictionary
* Run data quality checks to ensure the pipeline ran as expected
  * Integrity constraints on the relational database (e.g., unique key, data type, etc.)
  * Unit tests for the scripts to ensure they are doing the right thing
  * Source/count checks to ensure completeness

**Step 5: Complete Project Write Up**
* What's the goal? What queries will you want to run? How would Spark or Airflow be incorporated? Why did you choose the model you chose?
* Clearly state the rationale for the choice of tools and technologies for the project.
* Document the steps of the process.
* Propose how often the data should be updated and why.
* Post your write-up and final data model in a GitHub repo.
* Include a description of how you would approach the problem differently under the following scenarios:
  * If the data was increased by 100x.
  * If the pipelines were run on a daily basis by 7am.
  * If the database needed to be accessed by 100+ people.
 
 # Limitations
This project is just a simple start on creating a data model and several improvments exisits. Corrupt data, missing field and duplicate values should be captured and logged to a greater extent. Furthermore, more quality checks should be added. As of now the data model only use historical data. However, it would be even more interesting to look at newer data and update the data model on a monthly basis. Adding more data would require even more attention to the data quality as well as finding a reasonable way to automate the process.
