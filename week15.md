## Project Design based on new Moscow List

After gathering the new Moscow list from our client. We decide three main components for our data engine: a search engine, a data visualizer directly retrieved from the backend database, and a forum box which allows users to view and leave messages to share their experience.

## Search Engine

Two possible ways are provided in our team. One is search the index directly through SQL while the another one is through an open source search engine called ElasticSearch. 

For ElasticSearch, if is a distributed search and analytics engine.It is open source and can be used for all types of data.It is implemented in Java programming language and supports all operating systems having java virtual machines (J.V.M).It is the main component of Elastic Stack, which is a open source application for data analysis and visualization. It has high scalability and the speed of performing a action is also high which makes it a easy and fast tool for data analysis, processing and visualization.

Elasticsearch is actually a JSON document store built upon the Apache Lucene search engine. Lucene does its magic by indexing documents according to specific rules. We remember that databases like MySQL perform better in complex queries when tables are indexed - it's much the same idea.

Indexing in this context means that field values are mapped to documents or rows for faster searching, and both traditional row-store databases and indexing engines like Lucene/Elasticsearch can do it. Instead of having to search through the entire document or row space for a given value, the system can find that value in its internal index and immediately know which documents or rows contain it. This, of course, makes querying significantly faster.

Consdier the speed of execution, ElasticSearch would be the strategy in our project.

## Data visualization

Like the discussion in the search engine part, two possible solutions are also provided in this part. One is just use matplotlib while the another one is to use Echarts. 
ECharts as "A free, powerful charting and visualization library *". It is an open source visualization library implemented in JavaScript, runs smoothly on PCs and mobile devices, and is compatible with most current browsers. On the other hand, *Matplotlib** is detailed as "A plotting library for the Python programming language". It is a Python 2D plotting library which produces publication quality figures in a variety of hardcopy formats and interactive environments across platforms. It can be used in Python scripts, the Python and IPython shells, the Jupyter notebook, web application servers, and four graphical user interface toolkits. ECharts and Matplotlib can be primarily classified as "Charting Libraries" tools.

However, as the describtion above, echarts is more suitable in web. Therefore, Echarts became the soultion for data visualization part.

## Forum 

This part could help users to view and leave messages to share their experience. We decided just use the a bootstrap form here to support this functionality.
