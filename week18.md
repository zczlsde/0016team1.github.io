## This Week
The main progress in this week is to implement our search engine. We used the ElasticSearch and Haystack in our “Search” module, allowing users to query data from our database with a keyword. We used a technology called “inverted indexing” which automatically sort data with the relevance with our keyword. 

It is generally hard to only use the search engine to communicate with both backend and frontend. Therefore, haystack is used here, which provides the modular search for Django. Unified API allows Django to use to plug in different search engine without modifying the code. Solr, ElasticSearch, Whoosh, Xapian and so on are supported. ElasticSearch has really flexible and easy way to write the quries, which would be helpful for the communication with database, while solr could not achieve. As to the comparison between ElasticSearch and Whoosh, ElasticSearch is obviously the famous one with more functionalities, there is no reason to choose Whoosh as the search backend. All in all, the collocation of Haystack and ElasticSearch would be the strategy for our search engine.

To implement haystack and elasticsearch, haystack should be installed in the settings. The diagram below shows the details of installation. Name of the search engine, url of it and the name of index (which database) must be declared. Furthermore, realtimesignalprocessor means indexes would be updated automatically when the database is changed.
![](https://zczlsde.github.io/0016team1.github.io/Search.PNG)
Then, search_indexes.py is written to tell the haystack where to search and return the model or the searching query. In our project, we defines use_template and document are true, which means haystack would know which fields to index through an template and index only document. The directory to store this template is templates/search/indexes/AT_data. Only title is indexed to search the related articles.

In order to build the indexes successfully, ElasticSearch server must be run in the backend. We download 6.4.1 ElasticSearch locally and run the bat file in the bin folder to start the server. Then, run 'python manage.py rebuild_index' and all the indexes are created.

Next, communication between search backend and frontend must be feasible to achieve the search functionality. In the search.html, a bootstrap form is used to get the keyword that users input and send it back to the result fucntion in views.py. Once the keyword is received, related articles would be serched based on the indexes made before. Moreover, a paginator is implemented in our search engine. The maximum number of articles per page is set to 5 and page nubmer could be changed through this paginator. All the logics are written in the views.py under searchapp folder.

## Next Week

The plan for next week is to focus on the development of visualizer part and further develop the front-end stuff.

