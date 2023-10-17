# data-512-homework_2
The goal of this assignment is to explore the concept of bias in data using Wikipedia articles.  

## Project Goal 
For this assignment, a dataset of Wikipedia articles is combined with a dataset of state populations, a machine learning service called ORES is used to estimate the quality of the articles about the cities.  
An analysis is performed of how the coverage of US cities on Wikipedia and how the quality of articles about cities varies among states. The analysis will consist of a series of tables that show:  
The states with the greatest and least coverage of cities on Wikipedia compared to their population.  
The states with the highest and lowest proportion of high quality articles about cities.  
A ranking of US geographic regions by articles-per-person and proportion of high quality articles.  


## Data Source
The dataset that has been used for this analysis - https://drive.google.com/file/d/1khouDmMaZyKo0y5WkFj4lu7g8o35x_98/view
The Wikimedia Foundation REST API  was used to access page information data for Wikipedia articles. The latest revision ID was extracted from here.  
A machine learning system called ORES was used.  ORES is a machine learning tool that can provide estimates of Wikipedia article quality. The article quality estimates are, from best to worst:
FA - Featured article
GA - Good article (sometimes called A-class)
B - B-class article
C - C-class article
Start - Start-class article
Stub - Stub-class article


## API Documentation
In order to measure article traffic from 2015-2023, data was collected from the Pageviews API. 
Documentation - https://wikitech.wikimedia.org/wiki/Analytics/AQS/Pageviews  
Endpoint - https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end  
Terms of use of the Wikimedia Foundation REST API - https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions  
Further the following example notebook was used under the CC-BY license.  
Example Notebook - https://drive.google.com/file/d/1XjFhd3eXx704tcdfQ4Q1OQn0LWKCRNJm/view  
CC-BY License - https://creativecommons.org/licenses/by/4.0/  
 
## Environment
Jupyter was used in order to run a .ipynb Notebook. Any editor that allows .ipynb notebooks can be used to run this project following the installation of the modules specified in the code.

## License
This project is open-source and follows the MIT License. You are free to use and modify the code following the terms of the MIT License.

## Steps to Reproduce:
1)	Import the necessary Python libraries.  
2)	Run the Jupyter notebook which contains the code to retrieve the data from the google document and the APIs, preprocess it, upload it into the output files and create the necessary visualizations. 

## Errors Handled
The parameter safe='' was added to the urllib.parse.quote function so that it is able to handle cases where the movie name contains a special character

## Output Files 
The project generates three JSON output files. No intermediate files were created.  
academy_monthly_mobile_201507-202312.json: Monthly mobile access data.  
academy_monthly_desktop_201507-202312.json: Monthly desktop access data.  
academy_monthly_cumulative_201507-202312.json: Monthly cumulative data.  





