# Peer-graded Assignment: Segmenting and Clustering Neighborhood Data

### This repo contains two projects. 

#### Project 1:
The first notebook is a detailed analysis of Toronto city neighborhoods. Using the four square API, we extracted data on the different neighborhoods in Toronto, we focussed on the different locations of interest such as restuarants, coffee shops and bars. We then clustered the data to find out what the most common types of restuarant/bar were to each neighborhood. 


#### Project 2:
The second notebook explores where in London it would it be best to open a new restuarant. The analysis leverages the four square API to explore different neighborhood's in London. The following questions are answered; what restuarants recieve the best reviews? what restuarants are most popular, and what part of london are they in? Is there a type of restaurant that is consistently more popular than other's? This analysis will help anyone that wants to open up a restaurant in London and wants to know if it is a viable option where they intend on opening.


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


## Project Idea

My idea for the Capstone Project is to show that when driven by venue and location data from FourSquare, backed up with open source income data, that it is possible to present the cautious and nervous restuaranter with a list of possible locations to consider supplementd with a graphics showing the level of income in the region of the venue.

A high level approach is as follows:

1.The restuaranter decides on a city location [in this case London]
2.The ForeSquare website is mined for the top venues in the city
3.From this list of top venues the list is augmented with additional grographical data
4.Using this additional geographical data the top nearby restaurents are selected
5.The historical income level within a predetermined distance of all venues are obtained
6.A map is presented to the to the traveller showing the selected venues, income statistics of the area.
7.The future probability of a change in income happening near or around the selected top sites is also presented to the user
Who this solution is targeted at.
8.This solution is targeted at the cautious restauranter who is looking to set up a restuarant. The want to see all the main restaurant sites of a city that they have never visited before but at the same time, for whatever reaons unknown, they want to be able to do all that they can to make sure that they have indentified a suitable area where demand for their service will be high.

This project will include the following data science workflow processes:

Data Acquisition
Data Cleansing
Data Analysis
Machine Learning
Prediction


## Section 2: Data

**Data Description**
In this section, I will describe the data used to solve the problem as described previously.

As noted below in the Further Development Section, it is possible to attempt quite complex and sophisticated scenarios when approaching this problem. However, given the size of the project and for simplicity only the following scenario will be addressed:

Query the FourSqaure website for the top restaurant sites in London
Use the FourSquare API to get supplemental geographical data about the top sites
Use the FourSquare API to get top restaurant recommendations closest to each of the top site
Use open source London income data to provide the user with additional income data

