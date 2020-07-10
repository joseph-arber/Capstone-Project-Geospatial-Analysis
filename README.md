# Peer-graded Assignment: Segmenting and Clustering Geospatial Data with API

### This repo contains two projects. 

#### Project 1:
**What is there to do in Toronto?**
The first notebook is a detailed analysis of Toronto city neighborhoods. Using the four square API, we extracted data on the different neighborhoods in Toronto, we focussed on the different locations of interest such as restuarants, coffee shops and bars. We then clustered the data to find out what the most common types of restuarant/bar were to each neighborhood. 


#### Capstone Project:
**What part of London is the best place to buy a house?**
The second notebook explores where in London it would it be best to buy a new home. The analysis leverages the four square API to explore different boroughs of London. The following questions are answered; what boroughs have the best venues? what venues are most popular? Is there a type of venue that is consistently more popular than others? Does venue density affect property prices?

This analysis will help anyone that wants to open up a restaurant in London and wants to know if it is a viable option where they intend on opening.


# Capstone Project - The Battle of Neighborhoods

This file, and other associated files, make up my contribution to the final Peer Reviewed Assignment for the Coursera Capstone Project for Applied Data Science Capstone. This was my final module in the IBM Data Science Professional Certificate programme.

For reference I include the original definition for each part of the assignment.

### Part 1 [Week 1]
Clearly define a problem or an idea of your choice, where you would need to leverage the Foursquare location data to solve or execute. Remember that data science problems always target an audience and are meant to help a group of stakeholders solve a problem, so make sure that you explicitly describe your audience and why they would care about your problem.

This submission will eventually become your Introduction / Business Problem section in your final report. So I recommend that you push the report (having your Introduction/Business Problem section only for now) to your Github repository and submit a link to it.

### Part 2 [Week 1]
Describe the data that you will be using to solve the problem or execute your idea. Remember that you will need to use the Foursquare location data to solve the problem or execute your idea. You can absolutely use other datasets in combination with the Foursquare location data. So make sure that you provide adequate explanation and discussion, with examples, of the data that you will be using, even if it is only Foursquare location data.

This submission will eventually become your Data section in your final report. So I recommend that you push the report (having your Data section) to your Github repository and submit a link to it.

### Part 3 [Week 2]
In this week, you will continue working on your capstone project. Please remember by the end of this week, you will need to submit the following:

A full report consisting of all of the following components (15 marks):
Introduction where you discuss the business problem and who would be interested in this project.
Data where you describe the data that will be used to solve the problem and the source of the data.
Methodology section which represents the main component of the report where you discuss and describe any exploratory data analysis that you did, any inferential statistical testing that you performed, and what machine learnings were used and why.
Results section where you discuss the results.
Discussion section where you discuss any observations you noted and any recommendations you can make based on the results.
Conclusion section where you conclude the report.
A link to your Notebook on your Github repository pushed showing your code. (15 marks).
Your choice of a presentation or blogpost. (10 marks)


# Project Idea

**Business Problem**: London is a significant metroplitan area. As we all know London has some of the highest property prices in the world, we also know that certain boroughs have significantly higher average property prices than other boroughs, think Kensington and Chelsea compared to Barnet. 

Therefore imagine you were looking to buy a property in London with know apriori knowledge of the area; the variation in costs, the type of restuarants in an area, closeness to the center, what borough would you select and why? - Is it a borough with a lot of venues (venue density), lower prices, or closer to the city center? This project seeks to develop a data driven solution to analyzing london's property prices by borough and venue density. 

**Task**: To see if we can accurately predict London's house prices by borough based on the amount of rated venues within a location.

**Method**: Using the Four Square API to mine location data, we segment venues and locations based on the London borough they reside in. We then use these segments to cluster the data based on the average value of a property for each borough. We then map this data to geographically to explore the variation in house prices in respect to venue density.

Based on definition of our problem, factors that will influence our decission are:
* number of existing venues (restuarants, gym, places on interest) in the neighborhood 
* number of and distance to the venues in the borough, if any
* distance of borough from the city center
* type of venues in the borough (price, rating etc...)


A high level approach is as follows:

1. The home buyer decides on a city location [in this case London]
2. The ForeSquare website is mined for the top venues in the city
3. From this list of top venues the list is augmented with additional grographical data
4. Using this additional geographical data the top nearby venues are selected
5. The historical property price level within a predetermined distance of all venues are obtained
6. A map is presented to the to the home buyer showing the selected venues, property price statistics of the area.
7. The future probability of a change in property prices happening near or around the selected top sites is also presented to the user, who this solution is targeted at.
8. This solution is targeted at the cautious home buyer who is looking to buy a house in London. The want to see all the main    housing sites of a city that they have never visited before but at the same time, for whatever reaons unknown, they want to be able to do all that they can to make sure that they have indentified a suitable area where there is a high venue density and competitive prices.


This project will include the following data science workflow processes:

- Data Acquisition
- Data Cleansing
- Data Analysis
- Machine Learning
- Prediction


## Data

**Data Description**
In this section, I will describe the data used to solve the problem as described previously.

As noted below in the Further Development Section, it is possible to attempt quite complex and sophisticated scenarios when approaching this problem. However, given the size of the project and for simplicity only the following scenario will be addressed:

- Query the FourSqaure website for the top restaurant sites in London
- Use the FourSquare API to get supplemental geographical data about the top sites
- Use the FourSquare API to get top restaurant recommendations closest to each of the top site
- Use open source London income data to provide the user with additional income data.


### Data Acquisition: 

1. Four Square API venue data. Loaded data in JSON format then converted it to a pandas df.


2. London's property prices data from the london data store: https://data.london.gov.uk/dataset/average-house-prices The dataset contained the **'year', 'average value', 'borough', 'measure'**, we also added the latitude and longitude values for each borough in order to carry out the analyses. 


3. Geospatial data from http://martinjc.github.io/UK-GeoJSON/json/eng/topo_eer.json in JSON format allowed us to conduct the geospatial analyses, specifically mapping the property prices to the clustered location data.


### Package Dependencies:

- pandas
- numpy
- bs4
- matplotlib
- json requests
- folium
- sklearn
- geopy


# Discussion:

From the analyses conduced above we can seen that there is a lot of **variation** in London property prices. There is also a high venue density in London and a lot of the **venues** are located in. The key takeaway is that we have a number of variables to segment on. This thinking allowed us to **cluster** the data with the **K-means algorithm**, setting a higher K provided more interesting results but we must acknowledge the risk of **overfitting** in cases such as this.

After segmenting the data by clustering, we then performed data analysis on this information by adding the coordinates of the boroughs of London in relation to the average property prices of these boroughs. 

Future studies could perhaps take into account the quality of each venue, price and rating for instance. This could be an effective predictor of expected property prices. For instance, properties closer to mesuems and 5 star restaurants with great ratings could be far higher. Utlimatley this would improve our data driven decision making process.

