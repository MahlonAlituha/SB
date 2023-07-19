# SafeBoda rides cancellations analysis

## **Introduction**

This is an analysis of rides data as recorded by the safeboda app everytime a ride is ordered by a client, successful or unsuccessfully executed. Everyday a sigificant percentage of clients cancel their trip requests and we are trying to finf out why this is happening, how often it does happen and know potential actions to curb this as well as decrease these occurences. With a dataset that contains **fictional data** from SafeBoda, including trip dates, location, rider ID, arrival time, distance from client upon order, status of ride and other details. The goal is to carry out an analysis that will provide insight into the trends.

#### About the Data

The dataset is an excel file that contains two tables i.e. data dictionary and trip data with 163852 raws and 14 columns. We aswell have null entries and outliers that we shall need to get rid of.

#### Business Question

Task 1:

    1) What percentage of ride requests are cancelled?
    2) Sometimes after passengers have cancelled a ride, they immediately order another one. How could you try to calculate how often this happens? How often does that happen in this dataset? What fraction of customer journeys are cancelled and not re-ordered?
    3) Based on the current cancellation data, what are the most common reasons for passenger cancellations? Some ways to think about this might include - which days of the week have the highest cancelation rates? Which times of day? How long do passengers wait before they cancel a trip? What is the distance between the customer and driver?
          
Task 2:
    
    1) What further pieces of analysis might we want to run to understand more about passenger cancellation?
          
          ○ What data would you need?
         
          ○ How would this help you inform your analysis?

## Skills/Concepts applied:

    Data Cleaning
    Data analysis using Python
    SQL
    Data Visualization over Tableau
    Dashboard Building

#### Data cleaning 

The data cleaning involved getting rid of null values found in the dataset keeping data of only cancelled trips since it is where our analysis is based 

#### Data Analysis

Rides data was analysed, a variety of new dataframes were made using pyhton e.g. df_reoccurrence, which was attained by filtering 'passenger id' that appears more than once. This dataframe repeated client orders and it will be upon us to find out later if these re-orders occurred within a specified timeframe.

A must to convert the time columns into datetime format! Grouped the rows by passenger_id then found these time differences between reorders. In this particular analysis, we considered every order after under 5 minutes to be a reorder. Mathematical operations showing 94% rides are cancelled without reorder

Further analysis on waiting time before cancellation of the order is done with the minimum time being 1 second and the maximum 22 minutes. This is after the outliers upper 1% has been truncated because we assume no client would wait as long as 67 days before cancelling their order. 

A number of other metrics are analysed as well including subcounties with riders furthest away from order location. Katabi and Gombe wakiso have the fewest riders in place. Friday was noted as the day of the week with the most cancellations and 5pm as the hour of the day with most cancellations. This is probably due to scarcity of riders during rush hour.
