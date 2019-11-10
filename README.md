# Upgrading Google Trends's API: Viral Trends Clustering 

Google Trends provides robust data about the cultural interests of human populations, but it does not support a public API, and its two private research API’s are limited to 5 and 30 keywords per query, respectively.
 
To remedy this, we first upgraded a Google Trends scraper to accommodate theoretically infinite keywords per query. We then created a function that returns a list of all “viral” topics related to one query over a time period, where a “viral” topic is defined to be one that increased in search traffic volume a specified percentage over a controllable smaller time interval. Finally, we clustered these keywords into groups by applying a k-means learning algorithm to term frequency-inverse document frequency (TF-IDF) vectorized data, which reflects the relative importance of each word, scraped from Google Search.
 
To apply our upgraded Google Trends API, we analyzed the time-series interest of colleges and then the clustered viral keywords related to Harvard and MIT specifically. We reported that Harvard’s search volume can justify choosing Harvard because it’s “Harvard” and that the clustered viral topics show a divergence in the cultures of the two Cambridge institutions.

Read more about our results in our Medium post: 


## Getting Started

The rest of the notes will help you deploy the code on your machines. 

### Prerequisites

Python 3.7 or higher.
Packages: 
- Infrastructure: anaconda, jupyter notebooks, os, string
- Analysis: pandas, numpy, sci-kit learn, nltk
- Data Acquisition: Pytrends, beautiful soup, fake_useragents, urllib, requests 
- Visualization: plot.ly, tableau, matplotlib. 

### Installing

Run "git clone URL" in terminal to install the repository on your computer. Open the main directory in any IDE. 

### Understand the Directory

To Run:
- collegeMain.py : Has "get_pie_topics," the master function that returns clustered data given proper inputs. 
- PlotlyGraphing.ipynb : A Jupyter Notebook that plots and saves interest over time data for a list of keywords. 

To House Functions and Data: 
- collegeData.py : Holds college names, arrays, and locations. 
- googleSearchScraper.py : A functional document that scrapes Google results given input keywords. 
- googleTrendsUpgrade.py : The upgraded Google Trends API that can search infinite keywords and find related viral data.
- kmeansWordsAlgorithm.py : A functional document that clusters the results of the googleSearchScraper.py.
- /output/ : The destination for raw CSV files. 

To Visualize: 
- /images/ : This holds graphics and data visualizations.
- /Visualization-Tableau workbooks/ : The two workbooks used for the pie charts. 
- netflixPractice.py : Some quick visualizations of Netflix's virality results


## Built With

* [PyCharm](https://www.jetbrains.com/pycharm/) - The Python IDE
* [Jupyter Notebooks](https://jupyter.org) - For Data Visualization 
* [Plot.ly](https://chart-studio.plot.ly/feed/#/) - For Data Visualization

