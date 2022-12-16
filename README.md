欢迎提issue联系


Contents
0 Instructions 1
1 Activity 1 (60 points) 3
1.1 Sub-activity: Open Data COVID-19 API . . . . . . . . . . . . . . . . . . . . . . . . . 3
1.2 Sub-activity: Shaping the COVID data into different dataframes . . . . . . . . . . . . 5
1.3 Sub-activity: Aggregating, plotting, and analysing . . . . . . . . . . . . . . . . . . . . 6
2 Activity 2 (15 points) 9
2.1 Sub-activity: Graph creation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 10
2.2 Sub-activity: Graph manipulation and output . . . . . . . . . . . . . . . . . . . . . . . 11
3 Activity 3 (25 points) 15
3.1 Sub-activity: Loading and pre-processing of text data . . . . . . . . . . . . . . . . . . 15
3.2 Sub-activity: Applying NLP operations on the corpus . . . . . . . . . . . . . . . . . . 16
3.2.1 Stemming . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
3.2.2 Lemmatization . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
3.2.3 Finding synonyms and antonyms . . . . . . . . . . . . . . . . . . . . . . . . . 16
3.2.4 Bigrams and trigrams . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
3.3 Sub-section: Visualisation . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
3.3.1 Barplots . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
3.3.2 Heatmap . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17

0 Instructions
This document describes Coursework 2 of the 7CCSMCMP module. The coursework has three
activities, which focus on the main concepts covered in Weeks 7 to 11. We start with some general
instructions on how to format your answers for submission. Please read these instructions carefully before you start coding. They explain the correct format and documentation your solutions
must comply with. Coursework assessors may be not able to execute and assess code that does
not follow the instructions, which may lead to considerable penalties to your coursework mark.
Each of the three activities in the coursework must be addressed in a separate IPython notebook
file; you should submit a zipped file containing three notebook files with extension .ipynb, one per  

each activity.
Each notebook must be organised as shown in Figure 1. First, create a cell for all your library imports, and give it the title Imports with a markdown header. Then, if the activity has sub-activities,
organise the notebook into separate sequences of cells for each sub-activity using markdown headers. If the activity is not split in sub-activities, create a single markdown header called Activity
instead. Answer each task in a single cell, and give it a markdown header with the task number.
Tasks require you to write some code. Some tasks in Activity 1 ask you to provide explanations as
free text - write the explanations as comments at the end of the relevant cell.
Pleas,e use the proposed markdown headers to clearly signal each task solution cell to help the
markers assess your solutions correctly  



1.1 Sub-activity: Open Data COVID-19 API
The UK government has a portal with data about the Coronavirus in the UK; it contains data on
cases, deaths, and vaccinations on national and local levels. The portal is available on this page:
https://coronavirus.data.gov.uk. You can acquire the data by querying its API.
We ask you to use the requests library in order to communicate with the API. The documentation
is available at: https://docs.python-requests.org/en/latest. Read carefully the API documentation
at:
https://coronavirus.data.gov.uk/details/developers-guide/main-api.
Then complete the following tasks in order to acquire the data.
Task 1: Create a function get API data(filters, structure) that sends a specific query to the
API and retrieves all the data provided by the API that matches the query. The function
requires two arguments:
• filters (dictionary) are the filters to be passed to the query, as specified in
the API documentation. This will be a dictionary where keys are filter metrics and
values are the values of those metrics. For example, you may want to filter the data
by nation, date etc. As seen in the API documentation, filters are passed to the
API’s URL as a URL parameter. This means you will have to format filters inside
get API data in a way that the API can accept it as an argument.
• structure (dictionary) will specify what information the query should return,
again as specified in the API documentation. This will be a dictionary where the
keys are the names you wish to give to each metric, and the values are the metrics
as specified in the API. The structure argument specifies what attributes from the
records that match the filters you wish to obtain, such as date, region, daily casualties etc. The argument is passed as an URL parameter to the API’s URL. This
means you will have to format structure inside get API data in a way that the API
can accept it as an argument.  
