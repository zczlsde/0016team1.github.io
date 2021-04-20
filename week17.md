## This Week 

The main progress in this week is to set up our database. SQLite is used in this website which is a small scale database because there would have a large number of data to handle. Moreover, it is also the default database of Django framework and the installation details could be found in the setting.py under the AT_watch folder.

Communication between database and Django is through the model part in each aplication. Models.py is in under the folder of specific application and includes the desciption of tables and their fields. For example, the code below defines the main contents of project database, articles, which could be found under the AT_data. Fields like url and title are all declaimed here. Then, new model should be migrated. Simply run two commands in the terminal to do the migration, which are 'python manage.py migrate' and 'python manage.py makemigration'

![](https://zczlsde.github.io/0016team1.github.io/article_model.PNG)

After defining all the tables, data must be tranfered to the database. Commonly, a python file would be written to communicate with SQL database, while in Django framework, a shell would be used to execute the python file to transfer the data. The data files provided by the client are some csv files so a python file that could read the csv and transfer the data as well must be written.There is a file called transfer.py included the code that could transfer the contents in csv. As the diagram shown below, it is a progress that read a csv and insert the data to the database.

![](https://zczlsde.github.io/0016team1.github.io/transfer.PNG)

It is also possible to update the database through Django admin. There is an admin.py under each application and all the models that is required to view in the admin should be installed here. Then run 'python manage.py createsuperuser' to create an account and then visit the admin url locally and then log in the account. Next, the admin interface could be shown including all the data in the database.

## Difficulty and Future Plan

It is really hard to transer the csv file to the database without using the shell or admin. It would be convenient to use for admin if auto transfer is supported in this web. Then we would add new functionalities to support storing uploaded csv files and to display the database for illustration purpose. 
