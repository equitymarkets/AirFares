# Group Project 2 : ETL Project
## Transportation Data Integration 

### Project Proposal

#### Project Blurb

As a team, we decided to look into the transportation industry for our Extract, Transform, and Load Project. We decided to extract data from aviation transportation systems including information like passenger details, ticket prices history, airport traffic history and flight routes/trips, transform it into a standard and uniform format by cleaning the data to focus on the key things out project aims to highlights, and then loading this transformed data into a data warehouse: MongoDB in our casee it into a data warehouse.

#### Project Sources

For this project we will be pulling from two sources, both available from the U.S. Bureau of Transportation Statistics: 
1. Yearly fuel data : (https://www.eia.gov/dnav/pet/hist/eer_epjk_pf4_rgc_dpgD.htm) and  extensive
2. Yearly ticket price information (https://www.transtats.bts.gov/AverageFare/)
Both sources are available in csv format, over a 22 year period. We decided agaisnt using an additional dataset which contained and flight data including trips, routes, distance and arrival and departure cities, because of the size and scope of the files. However we were able to draw some meaningful insights from the dataset which further informed the analysis and appraoch we adopted in our project. 

For the database we will be using NoSQL, or non-relational database specifically, MongoDB with PyMongo. After cleaning, the csv's will be loaded through the terminal in the resources folder that holds the csvs, then analyzed using a Jupyter Notebook. 

Our overaching goal is to investigate the possibility of a correlaton between fuel and ticket prices through an extensive timeframe which encapsulates major impact-having-events including 9/11 of 2001, the Great Financial Crises of 2007 and the  2020 Covid-19 Pandemic.

#### Project Report

There were several challenges in extracting and transforming the data. 
The passenger and airline price CSVs were not formatted to cleanly fit into a database format. To clean them, we had to delete the top row as well as the bottom three rows. 

