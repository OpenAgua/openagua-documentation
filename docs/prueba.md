For now, this documentation is organized around the main user areas of the website, focusing on technical aspects (technologies involved, methods used, etc.), but also use in some cases. General help for the registered user is found on the site itself, under "Help".

## Orientation

All the projects and networks are stored in the library called **Home**. In here, the user will be able to create new networks and arrange them by the user's preferences. Networks can be shared, edited, exported, deleted and cleaned.


#### Manage

The "Manage" section allows the user to manage HP _projects_, _networks_, and _templates_.

The overall steps in creating a project + template + network are as follows (main HP functions involved in parentheses):
1. Add a project (*add_project*)
2. Add a network (*add_network*), selecting a template to add at the same time. The only available template for now is "OpenAgua"; this is created automatically if it doesn't already exist. During network creation, a default "Baseline" scenario (*add_scenario*) is created for the new network, similar to Hydra Modeller. 

For project/network creation, HP functions are called as follows:
1. *add_project*
2. *add_network*
3. *apply_template_to_network*
4. *add_scenario*


## Project & Network Creation

#### Projects

* **Add Project**: This uses HP's _add_project_ function.

#### Networks
Once you are logged-in, click "add network" in order to start building your project. A window will pop up so you can name and describe your project. Each network can have different versions where you will be able to switch within without loosing any data, we recommend selecting the latest version and looking at the "version history" link before modifying the template. This feature will function in later versions of OpenAgua.

Once your network is set you can start building it by clicking OVERVIEW, also a drop-down menu is shown at the upper right where sharing and editing functions are available.

* **Add Network**: This uses HP's _add_network_ function with the user's active project.

#### Templates

The OpenAgua user cannot currently add a template via the interface.

##Setting the study area

#### Network Editor
The Network Editor section is destined to construct your model in a schematic view. First zoom in to select the geographic area of your project. There are a set of different map types (light, terrain, satellite, etc.) on the right side of your map, pick the one that best suit your project. 

Once you set the area, start adding nodes and links. To set a point or a node: Click on the marker and place it on the map, a feature window will appear and here you have to select the type of feature, name and description. To set a link/river/conveyance: Click on the line icon located at the top left of your map, then click anywhere in the map to start building your polyline, do a double-click on the last point to finish your polyline or simply press finish on the right side of the line icon.

You are also able to edit the schematic location of points and polylines just click the edit icon at the top left of the map and move your nodes and links freely then save any changes. ****** It is important to know that every polyline is managed as an independent link (we have to discuss this part).***** On the other side if you want to edit the nature of any node or link, do a right click on it and you will be able to: see the coordinates of the feature and center the data there. Moreover you will be able to delete, edit the name/description and data of the feature.

* **Add node**: The HP functions *add_node* is used, with the user's active *network_id*.
* **Add link**: The HP function *add_link* is used, with the user's active *network_id*.


##Elements of the schematic model 

**Demand Sites**

**Catchments**

**Miscelanoeus Sources and Reservoirs**

**Rivers, Diversions and Conveyance**

**Delivery Link and Return Flow**


#Data

## Data Editor

The basic data editor consists of three areas:

1. Variable selector,
2. Data editor and
3. Data preview

### Variable selector
The variable selector consists of dropdowns using [**boostrap-select**](https://silviomoreto.github.io/bootstrap-select/).

### Basic Data editor

The basic data editor differs from the advance data editor in terms of the nature of data.  

Currently, the data editor only allows editing the "descriptor" field of the database. Text data is displayed and edited using the [**Ace** code editor](https://ace.c9.io).

Python code is entered here. This code is evaluated using the evaluate function found in evaluator.py. Essentially, a string representation of a function is created, with the entered code as the body of the function. All lines are indented appropriately as needed for Python. The function is then called by the evaluator and assigned to a variable. The function is run once per time step.

The last line of the user-entered code is automatically prepended with "return ", such that the user doesn't need to. This is most useful for simple cases, such as a constant value:

```
5
```

However, the evaluator also automatically detects the presence of a "return " in the last line, such that the user may also include a return as desired. So `return x` on the last line is the same as `x`. In many cases, including `return` is simply a matter of personal preference. But this is particularly useful if a return is nested in the last part of a conditional statement. To demonstrate, the following three versions of code input yield the exact same result when evaluated:

```
if date.month in [6,7,8]:
    x = 0.5
else:
    x = 1
x
```
```p
if date.month in [6,7,8]:
    x = 0.5
else:
    x = 1
return x
```

```python
if date.month in [6,7,8]:
    return 0.5
else:
    return 1
```

This scheme enables the user to import, enter custom functions directly into the code, etc. In the future, this will also enable offering a range of custom Python functions. It will also allow the user to create, store, re-use, and share custom functions.

The last three examples above should raise a question: where does "date" come from? OpenAgua will include several built-in variables available for use. For now, this only includes the date of the function call. In the future, however, this will expand to include others as needed.

### Advanced Data editor
The advanced data editor is a powerful tool to input data, it is based on using a pivot table to arrange all data and information. By using pivot tables, this editor gives the user flexibility and analytical skills resulting on well-organized source data.

To start using the advanced data editor first identify the filters bar and select the feature, variable and scenario. In here the user is able to select more than one data to edit. Click Load to boot your pivot table. Start dragging features to the row and column bank. Notice there is a drop down menu of aggregators, by using this, data is set to be original, average or a sum. Arrange your table as you prefer and start filling it either manually or by copy-paste from another data sheet. There is an extra button called Block, this allows to add columns to every feature of the table which might be useful for adding more data to specific variables. The user is able to make as many pivot tables as it like, just save your set up and open it at any time.

The key limitation of this pivot table is it may become unstable or unusable after 100,000 rows of data. If you reach the limit you will be warned to use the filter at the top to help reduce the amount of data retrieved from the server. This filter enables you to select more specific data based on an arrange of filter criteria including feature type and variable.

To know more about pivot tables look at UI Tutorial (https://github.com/nicolaskruchten/pivottable/wiki/UI-Tutorial)


## Scenario Builder

Not built yet.

## Model Dashboard
The model dashboard enables you to run models for one or more scenarios. Once the model is run, progress will be reported in one or more progress bars. Additionally, more detailed information about both, the model run as a whole and about each specific scenario run is shown.  The main log information is always shown providing feedback including the parameters used in the current model run (e.g. time span, level foresight, scenario ids, solver etc.) and the general status of the model run. 

The Scenario log is shown by cilcking the view log button next to the progress bar. It provides text updates about the model run. Additionally, it provides limited information from Pyomo about the optimization problem (e.g. number of objectives, constraints, variables etc.) Importantly this information also includes the status of the problem after the model run including specifically the termination condition. Termination conditions could include optimal, infeasible and many others (see http://www.pyomo.org/blog/2015/1/8/accessing-solver).

During the run, the modeling can be stopped by clicking Stop model.

## Data Exporter

Not built yet. This might be best deferred to the Hydra Platform Web Interface.


#Results
## Results Explorer / Chart maker
The results explorer consists of:

* A suite of pivot tables and charts

* Options to change the plot renderer (Plotly and Google Charts)

* Options to filter the data from the server. 

* The ability to save charts for later viewing and editing.

First, select in the filters bar the feature or variables and click load. Then select which kind of plot you prefer from the suit of charts and tables at the drop down menu. Select the type of aggregator and then start building your results pivot table.

To add dynamism, there are two render options in which the user is able to see and edit their results: Plotly and Google charts. Both are online analytics and data visualization tools, find this option on the drop down menu located at the top left corner then select the most adequate for your project. If you want to change from one render to another remember to click Load after switching this option.

**Plotly:** By hovering the pointer on the chart, an edit menu will appear at the right corner of your plot. Here you will be able download your result, zoom in and out, edit etc. If you choose to edit your plot, it will automatically take you to the plotly site where you will be able to style and analyze it with several statistical tests.

**Google Charts:** To activate the editing options double click in any place of the chart. A pop-up window will appear so that you can change the type of chart, font style and size etc.


Note: To create a scatter chart the filter should be used to select more specific data.


## Chart Maker

Not built yet. For now, there is an example chart built using [**Plotly**](http://plot.ly). The intent is to build a control panel for building Plotly graphs.

## My Charts or Chart Collection

The chart collection contains all the saved graphs and plots from the results explorer window. By clicking View on the image, a slide show will display the selected image. If there are some changes to be performed, simply click edit and this command will take the saved result into the Results Explorer window in order to perform any modification.

## Decision Dashboard

Not built yet.

