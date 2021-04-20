## This Week

We finished the development of visulizer part and forum part. Furthermore, detailed information was provided on the first page of our website.

We selected the open-source software Echarts to help plot and display data visualisation results on our webpage. It’s a light weighted java-script module which is designed for various visualisations. (Please see their website for more examples)
Here is the component we used to set up the graphic displayers:

![](https://zczlsde.github.io/0016team1.github.io/vs_set_up.jpg)

The piece of code first created a container to hold the graphic frame and initialise it using the Echarts built-in functions. We have included the source file for display in the first two lines and they can be subject to changes for different versions. Further modifications will also be calling the same function to update. The function will plot a new graph on the same location and erased the previous image plotted. The parameter “config” used here is retrieved from our back-end server and the interaction will be displayed shortly.

![](https://zczlsde.github.io/0016team1.github.io/ajax.jpg)

Here is an example we use the “ajax” property from JQuery to refresh only the selected part of our website, in this case, the graph displayer. It sends a post request, with specific headers, to our back-end server and refresh the graph displayed only when configuration seetings are successfully retrieved. We also add the “ready” property to this function so that it stays idle and only operates when the button is pressed.
To set up a graph properly, we used a builder design pattern to assemble the settings. The setting base class is “option.py” and the class “Option” can be inherited or extended for configuration settings. The following graph is an example of how we assembled the “lined-chart” and “smoothed-line-chart” graph. The rest of the properties are the same but the “smoothed” version changed a setting in the base “line-chart”. The data displayed is modified in a similar way, passing a parameter to overwrite the default value in the settings.

![](https://zczlsde.github.io/0016team1.github.io/config_builder.jpg)
In some of the cases, the data displayed are extracted from our database. But due to the limitation of numerical data in our database, we hard coded some of the values in the visualiser, for example the “linked-chart” and the “tree-diagram” to show the capability of this component.
For the complete list of Echarts configurations, please visit here.

Moreover, The forum part is constructed by bootstrap tables. Forumresult.html is the main page when you click the forum button on the top. A for loop is used to tranverse all the submitted forums and shows them to the users. A button is added at the bottom for users who want to leave a message. Forum.html could get the input of users through the bootstrap form and send them to the forum function in the views.py under forum folder. This function could store this information to the database.

## Future Plan
Meet the client to do the final check and try to finish the report website.
