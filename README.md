# Group Project 2 : ETL Project
## Transportation Data Integration 

### PROJECT PROPOSAL

#### PROJECT BLURB
This project involves building a data pipeline that extracts data from various sources, transforms it into a suitable format, and loads it into a target database or data warehouse.

As a team, we decided to look into the transportation industry for our Extract, Transform, and Load Project. We decided to extract data from aviation transportation systems including information like passenger details, ticket prices history, airport traffic history and flight routes/trips, transform it into a standard and uniform format by cleaning the data to narrow the focus on the key things our project aims to highlight, and then loading this transformed data into a data warehouse: MongoDB in our case. 

#### PROJECT SOURCES

For this project we will be pulling from two sources, both available from the U.S. Bureau of Transportation Statistics: 
1. Yearly fuel data : (https://www.eia.gov/dnav/pet/hist/eer_epjk_pf4_rgc_dpgD.htm) and
2. Yearly ticket price information (https://www.transtats.bts.gov/AverageFare/)

Both sources are available in csv format, over a 22 year period. 

We decided agaisnt using an additional dataset (https://diybigdata.net/2019/12/airline-flight-data-analysis-data-preparation-reprise/) which contained extensive flight data including trips, routes, journey distances and arrival and departure cities, because of the size and scope of the files. However, we were able to draw some meaningful insights from the dataset which further informed the analysis and approach we adopted in our project. 

#### PROJECT DATABASE

For the database we will be using NoSQL, or non-relational database specifically, MongoDB with PyMongo. After cleaning, the csvs will be loaded through the terminal in the resources folder that holds the csvs, then analyzed using a Jupyter Notebook. 

#### THE PROJECT IN STEPS

**Step One**: The project will begin by collecting data on jet fuel prices and airline ticket prices from our sources highlighted above. The data will then be cleaned and transformed to ensure that it is consistent and accurate. This process involves removing duplicate records, handling missing data, and standardizing data formats.

**Step Two**: Once the data has been cleaned and transformed, it will be loaded into a database for analysis. The analysis will involve using statistical techniques to identify any correlations between jet fuel prices and airline ticket prices. The project will also investigate whether major global events, such as natural disasters or political crises, have an impact on airline ticket prices and to what extent. Our analysis will also shine light of seasonal ticket prices. ie: which parts of the years are tickets cheapest and most expensive.

**Step Three**: The results of the analysis will be presented in a report, which will include visualizations and explanations of the findings. The report will provide the insights we deducted in step two and this information can be potentially useful for airlines and other industry stakeholders in making pricing and business decisions as well as individuals trying to make informed decisons on when to purchase plane tickets.

#### THE BOTTOM LINE

Our **overaching goal** is to investigate the **possibility of a correlaton between fuel and ticket prices** through an extensive timeframe which encapsulates major impact-having-events including 9/11 of 2001, the Great Financial Crises of 2007 and the 2020 Covid-19 Pandemic. We will also like to draw some seasonal patterns in our air-tickets data concerning fluctuations in prices throughout the year.


### PROJECT REPORT

#### I. Average Fares Data Transform

Steps implemented include:
1. Numpy as Pandas was imported.
2. To read in all of the AverageFare_Annual csv files, a 'for loop' was created to loop through each file. 
3. As the dataframes were created they were appended to a list. Some files needed to be edited (mainly using the skiprows() method, in order to maintain the proper column headings. 
4. From this list of dataframes, we took the Average Fare ($) column from each of the ten most popular airports and appended them to their own list using a 'for loop'. 
5. A nested 'for loop' was then implemented in order to convert all values to floats. 
6. Once we had ten lists, for each of the ten airports we chose within the time frame of 2000 to 2021, we converted these into a dataframe. 
7. Since each airport is a column, the dataframe is transposed so each airport is a row instead for clarity and better readability of the data.
8. The dataframe is then exported to the Resources folder as a csv file. 


#### II. Jet Fuel vs Ticket Prices

Steps implemented include:
1. Dependencies Imported (pymongo, pandas, matplotlib, pprint etc)
2. Checking to make sure our database was loded into MongoDB 
3. Setting up a Pandas DataFrame for fuel price
4. Setting up a Pandas DataFrame for fare prices
5. Creating a Pandas Series using yearly average prices from the 10 busiest US airports
6. Creating a Series for fuel prices, averages are grouped by all possible days for each year (about 250 / year)
7. Combining average fare prices with average fuel prices, 2000-2021 using the 'concat()' method.
8. Dividing fare price by fuel price to show a real decrease in air fares vs. price of jet fuel

<img width="661" alt="Screenshot 2023-03-23 at 9 35 01 PM" src="https://user-images.githubusercontent.com/114604829/227402099-b8d57085-52b9-4e8b-a7c1-c23e23d8267b.png">

## (insert point 8 analysis here)


<img width="664" alt="Screenshot 2023-03-23 at 9 32 19 PM" src="https://user-images.githubusercontent.com/114604829/227401750-970a3dbf-fc9c-4d54-955a-a35f9099b4a0.png">

While glancing at the dataframe you can see that fare prices, in nominal terms, have dropped but the difference is even more pronounced when you plot the nominal price over fuel costs. While lows were reached in 2007, this ratio, up until 2021, was falling.

#### OUR CONCLUSIONS




#### PROJECT LIMITATIONS AND SETBACKS

During our project we encountered some limitations and setbacks that we have chosen to highlight below: 

1. Because we cleaned our data to not be split by days, months, and years and just maintained a yearly breakdown, our deductions aren't based on 'longitudinal anaysis' like week-to-week or month to month analysis. This can potentially lead to undue emphasis placed on our coclusions. 
2. Because our sources came from two different places, a lot of work had to go into reformatting both datasets so they are able to merge smoothly for analyses.
3. The passenger and airline price CSVs were not formatted to cleanly fit into a database format. Thus we had to clean them by deleting the top and bottom three rows. 
The passenger and airline price CSVs were not formatted to cleanly fit into a database format. To clean them, we had to delete the top row as well as the bottom three rows. 

