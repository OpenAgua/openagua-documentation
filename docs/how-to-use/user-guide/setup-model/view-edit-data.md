# View/edit data

Two tools are provided for entering data. First, the [**Single Data Editor**](https://github.com/openagua/openagua-documentation/tree/f19ba5dcd6e831142525f48888c806f2925f6afe/user-guide/entering-data/README.md#single-data-editor) allows input of data on a per-scenario, per-resource, per-variable basis. In contrast, the [**Multi Data Editor**](https://github.com/openagua/openagua-documentation/tree/f19ba5dcd6e831142525f48888c806f2925f6afe/user-guide/entering-data/README.md#multi-data-editor) allows input for multiple scenarios/resources/variables at once, using a pivot table-style input mechanism. The Single Data Editor allows for advanced custom input. The main utility of the Multi Data Editor is to copy-paste multiple time series data at once.

## Single Data Editor

The basic data editor consists of three areas:

1. Resource & scenario selector
2. Variable selector
3. Data input
4. Data preview

### Resource & scenario selector

### Variable selector

### Data input

Python code is entered here. This code is evaluated using the evaluate function found in evaluator.py. Essentially, a string representation of a function is created, with the entered code as the body of the function. All lines are indented appropriately as needed for Python. The function is then called by the evaluator and assigned to a variable. The function is run once per time step.

The last line of the user-entered code is automatically prepended with "return ", such that the user doesn't need to. This is most useful for simple cases, such as a constant value:

```text
5
```

However, the evaluator also automatically detects the presence of a "return " in the last line, such that the user may also include a return as desired. So `return x` on the last line is the same as `x`. In many cases, including `return` is simply a matter of personal preference. But this is particularly useful if a return is nested in the last part of a conditional statement. To demonstrate, the following three versions of code input yield the exact same result when evaluated:

```text
if date.month in [6,7,8]:
    x = 0.5
else:
    x = 1
x
```

```text
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

This scheme enables the user to import, enter custom functions directly into the code, etc. In the future, this will also enable offering a range of custom Python functions \(Check **Writing Functions**\). It will also allow the user to create, store, re-use, and share custom functions.

The last three examples above should raise a question: where does "date" come from? OpenAgua will include several built-in variables available for use. For now, this only includes the date of the function call. In the future, however, this will expand to include others as needed.

### Data preview

## Multi Data editor

The advanced data editor is a powerful tool to input data, it is based on using a pivot table to arrange all data and information. By using pivot tables, this editor gives the user flexibility and analytical skills resulting on well-organized source data.

To start using the advanced data editor first identify the filters bar and select the feature, variable and scenario. In here the user is able to select more than one data to edit. Click Load to boot your pivot table. Start dragging features to the row and column bank. Notice there is a drop down menu of aggregators, by using this, data is set to be original, average or a sum. Arrange your table as you prefer and start filling it either manually or by copy-paste from another data sheet. There is an extra button called Block, this allows to add columns to every feature of the table which might be useful for adding more data to specific variables. The user is able to make as many pivot tables as it like, just save your set up and open it at any time.

The key limitation of this pivot table is it may become unstable or unusable after 100,000 rows of data. If you reach the limit you will be warned to use the filter at the top to help reduce the amount of data retrieved from the server. This filter enables you to select more specific data based on an arrange of filter criteria including feature type and variable.

To know more about pivot tables look at UI Tutorial \([https://github.com/nicolaskruchten/pivottable/wiki/UI-Tutorial](https://github.com/nicolaskruchten/pivottable/wiki/UI-Tutorial)\)

