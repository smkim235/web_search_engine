# Web Search Engine
## for the mathematics department at Brown University

by Semin Kim. Last Update: 2017/01/05.

We implement a web search engine for the department of mathematics at Brown University.

1. Crawler
    * Use BeautifulSoup for HTML parsing.
    * BFS through link information. 
    * Visit pages whose hostname ends with 'math.brown.edu'.
    * Scrape only text pages and skip pages like pdf and image files.  
1. Indexing
    * Use SQLite for a database. 
    * Use an inverted index for a schema. 
1. Word Process
    * Use NLTK.
    * Apply the Porter stemming and remove English stopwords for words in indexing and querying.
    * Use only alphanumeric character for simplicity. (limitation: 'info@math.brown.edu' is parsed as 'info math brown edu')
1. Search and Ranking
    * Retrieve pages that contain every word in a query (after stemming and removing stopwords).
    * Use the PageRank algorithm to rank matched pages.
    * To maintain the Markov property, transfer the probability of links toward an outside of math.brown.edu to the original page. 
1. TODO
    * Improve the ranking algorithm by combining methods, such as word frequency, word location, and link text together with the  PageRank algorithm with appropriate weights. 
    * Use id instead of raw data for database space efficiency.
    * Add a feedback routine such as learning from click to improve ranking. 

*Reference*
* Zhai, C & Massung, S. (2016). *Text Data Management and Analysis*. ACM Books.
* Raschka, S. (2015). *Python Machine Learning*. Packt Publishing. 
* Segaran, T. (2007). *Programming Collective Intelligence*. O'Reilly.
