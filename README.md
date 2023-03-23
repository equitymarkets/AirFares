# Group Project 2

## Project Proposal

For this project we will be pulling from two sources, both available from the U.S. Bureau of Transportation Statistics: yearly fuel data () and yearly ticket price information (https://www.transtats.bts.gov/AverageFare/), both available in csv format, over a 22 year period. 

For the database we will be using NoSQL, or non-relational database specifically, MongoDB with PyMongo. After cleaning, the csvs will be loaded through the terminal in the resources folder that holds the csvs, then analyzed using a Jupyter Notebook. 

We are looking to find out if there is a correlation between ticket prices and fuel prices, through various timeframes, including 9/11, the Great Financial Crisis, and the COVID pandemic. 

## Project Report

There were several challenges in extracting and transforming the data. The passenger and airline price CSVs were not formatted to cleanly fit into a database format. To clean them we had to delete the top row as well as the bottom three rows. 

