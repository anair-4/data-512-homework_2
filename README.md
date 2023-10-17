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
In order to measure article traffic from 2015-2023, data was collected from the MediaWiki Action API. 
Documentation - https://www.mediawiki.org/wiki/API:Info
Terms of use of the Wikimedia Foundation REST API - https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions  
Further the following example notebook was used under the CC-BY license.  
Example Notebook for Getting Page Info - https://drive.google.com/file/d/15UoE16s-IccCTOXREjU3xDIz07tlpyrl/view
Example Notebook for the ORES API - https://drive.google.com/file/d/17C9xsmR9U3lJeD52UTbAedlHDetwYsxs/view
CC-BY License - https://creativecommons.org/licenses/by/4.0/  
 
## Environment
Jupyter was used in order to run a .ipynb Notebook. Any editor that allows .ipynb notebooks can be used to run this project following the installation of the modules specified in the code.

## License
This project is open-source and follows the MIT License. You are free to use and modify the code following the terms of the MIT License.

## Steps to Reproduce:
1)	Import the necessary Python libraries.  
2)	Run the Jupyter notebook which contains the code to retrieve the data from the google document and the APIs, preprocess it, upload it into the output files and create the necessary visualizations. 

## Errors Handled
Since the number of requests was so high, the API would stop responding after every 3000-4000 requests with a 429 error code signifying too many requests. So, the dictionary was saved into a file in order to save the responses that were given and then the function was run again to update the doctionary with the remaining values. The process takes about 7 hours in total.

## Output Files 
The project generates one JSON output file and multiple intermediate JSON files which were used to save intermediate outputs. The final output of each of the analyses are embedded in the notebook.  
wp_scored_city_articles_by_state.csv: Final combined dataset for analyses.  

Schema -   

|Columns           |  
| ---------------- |
|state             |  
|regional_division |  
|population        |  
|article_title     |  
|revision_id       |  
|article_quality   |  


Intermediate Files - 
rev-id-details.json - contains the revision ID for each article  
score-details.json (1-6) - contains the response of the ORES API   

## Research Implications

As part of this project, I was able to acquire data using APIs which gave me insight into some of its limitations and best practices like ensuring that the API isn't called too many times an hour. I realized that the "too many requests" error was propbably to ensure that no individual gets an unfair share of the resources that were meant to be used by everyone. Moreover, exploring geographic biases that are represented in data even in a well-resourced country like the US gave me great insight into how prevalent bias is and how important it is to explore, identify and remove it to create fair and equitable systems. 

1. What biases did you expect to find in the data (before you started working with it), and why?  
A bias that I expected to find in the data before I started working with it using the information from the introduction in class was that places that were more travelled to or visited would have a better classification as there would be more contributions for those articles. I also expected to see large cities that are considered "hubs" for various industries to have a better classification.

2. What might your results suggest about (English) Wikipedia as a data source?
Wikipedia is a valuable resource for general information, providing a vast quantity of data with citations. However, its reliability and neutrality may vary. Although Wikipedia seems to have some strict rules around verifiability, the fact that it is community edited can open it up to inaccuracies and bias. Hence, it does not seem like an appropriate data source for academic research.

3. How might a researcher supplement or transform this dataset to potentially correct for the limitations/biases you observed?
Researchers could supplement this dataset a number of ways. One would be to consult an expert about the specific geographic or demographic factors being studied. Second, they will have to conduct additional data acquisition from several other sources. Lastly, they must highlight limitations and transparently report the dataset's limitations and biases in research publications to ensure that users and readers are aware of the data's context and potential constraints. 









