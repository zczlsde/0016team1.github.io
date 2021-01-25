## Design of Database
A vital part of this project is to design tha structure of tables in our database.
Whole logic our database would follow thirteen csv files gotten from our clients.
There are 415 files in the main csv file called Articles and our analysis would based on these.
Some of the tables and fields are not necessary in our project so they are not included in our models.
Currently, only six tables are included in our database design, table name and its fileds are shown below:

Location: name = models.CharField(max_length=200)
Source: uri = models.CharField(max_length=500, unique=True)
        name = models.CharField(max_length=500)
        source_importance = models.IntegerField()
        alexa_global_site_importance = models.IntegerField(null=True, blank=True)
        alexa_country_site_importance = models.IntegerField(null=True, blank=True)
        location = models.ForeignKey(Location, on_delete=models.CASCADE, null=True, blank=True)
Link: url = models.URLField(unique=True)
SocialMediaSharing: facebook_shares = models.IntegerField(null=True, blank=True)
                    google_plus_shares = models.IntegerField(null=True, blank=True)
                    pinterest_shares = models.IntegerField(null=True, blank=True)
                    linkedin_shares = models.IntegerField(null=True, blank=True)
Author: uri = models.CharField(max_length=500, unique=True)
        name = models.CharField(max_length=500)
        is_agency = models.BooleanField()
Article: url = models.URLField()
         title = models.CharField(max_length=1000)
         body = models.TextField()
         datetime_published = models.DateTimeField()
         language = models.CharField(max_length=3)
         data_type = models.CharField(max_length=4, help_text="news, blog or pr")
         image = models.URLField(null=True, blank=True)
         source = models.ForeignKey(Source, on_delete=models.CASCADE)
    l    links = models.ManyToManyField(Link)
         location = models.ForeignKey(Location, on_delete=models.CASCADE, null=True, blank=True)
         authors = models.ManyToManyField(Author)
         shares = models.ForeignKey(SocialMediaSharing, on_delete=models.CASCADE, null=True, blank=True)
         datetime_found = models.DateTimeField()
         is_duplicate = models.BooleanField(default=True)
         original_article = models.ForeignKey('Article', on_delete=models.CASCADE, null=True, blank=True)
Primary key would be created by Django model directly, while foreign key and manytomany field are described in model definition.

## Update of our code:
The first action to our code is to return the original version and recreate Django project because of misunderstanding of Django model.
Then, all definitions of models designed currently are declared in models.py of class AT_data (Create by startapp).
Next, AT_data is added in installed app of setting.py and makemigaration and migrate instructions are executed by manage.py.
In order to manage our database well, admin is installed by creating a superuser and also create model class in admin.py.
By running python manage.py shell, csv files could be tranfered here.
This week, Location and Source are transfed in.
Through python manage.py runserver, these two tables could be viewed and edited in admin.

## Current Difficulties
1. Frountend, static files containing css, js and html files should be put in.
2. Deal with many to many relations.
3. Excel is not familiar. Some csv files should be edited by excel in order to tranfer data easily.
