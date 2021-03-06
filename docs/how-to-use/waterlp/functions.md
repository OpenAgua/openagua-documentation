# Functions reference

The following functions are available for use within WaterLP.

### `get`

Get data from another variable, or another time step, possibly aggregated.

#### Arguments

| Argument | Data type | Description |
| :--- | :--- | :--- |
| `path` \(required\) | string | The path of the variable \(aka attribute\) of interest. See note below for more detail on path construction. |
| `flatten` | boolean | Whether or not the value returned should be summed across multiple columns if the variable obtained is a multi-column dataset. Currently, most datasets are single columns, so this normally will not be used. Defaults to `True`.  |
| `offset` | integer | Get a value from a specific time step offset. Values can be negative or positive. E.g., `offset=-1` returns the value from the last time step, while `offset=1` returns the value from the last time step. Offset values beyond the range of the data will result in `None`. Default is `0`. |
| `start` | date string  or Pendulum date | This indicates that the value should be aggregated from more than one time step, with start indicating the start date of the aggregation period. The value should be either a [Pendulum](https://pendulum.eustace.io/) date object or a string \(e.g., `1999-10-01`\) that Pendulum can properly parse. Future `start` values are valid, though should be accompanied by a future `end` value as well. Default is `None`. |
| `end` | date string or Pendulum date | This indicates that the value should be aggregated from more than one time step, with `end` indicating the end date of the aggregation period. The value should be either a [Pendulum](https://pendulum.eustace.io/) date object or a string \(e.g., `1999-10-01`\) that Pendulum can properly parse. Future `end` values are valid. Default is `None`. |
| `agg` | string | If aggregating a value \(i.e., with `start` and/or `end)`, this indicates how the value should be aggregated. Options include `mean` and `sum`. Default is `mean`. |

#### Returns

A scalar representing the value of the target variable during the time step.

#### Notes

Currently, path names are constructed in one of two ways, depending on the resource type. For _nodes_ and _links_:

**Example 3**: Get the mean water year runoff-to-date.

```python
# Assume water year starts Oct. 1.
start_date = '{wy}-10-01'.format(wy=water_year-1)
get("Monterrey/node/Catchment Rio San Juan/Runoff", start=start_date, agg="mean")
```

`"[network_name]/[resource_type]/[resource_name]/[attribute_name]"`

where network\_name is the name of the network \(of course!\), resource\_type is either node or link, resource\_name is the name of the node or link \(e.g., El Cuchillo Reservoir\), and attribute\_name is the name of the variable \(e.g., Storage Capacity\).

For network attributes \(global variables ascribed to the system as a whole, as opposed to a specific resource or facility\):

`"[network_name]/[attribute_name]"`

#### Examples

**Example 1**: Get the runoff from a catchment in the current time step.

```python
get("Monterrey/node/Catchment Rio San Juan/Runoff")
```

**Example 2**: Get the reservoir storage from the previous time step.

```python
get("Monterrey/node/El Cuchillo/Storage", offset=-1)
```

**Example 3**: Get the mean runoff-to-date for the current water year.

```python
start_date = "{year}-10-01".format(year=water_year-1)
get("Monterrey/node/Catchment Rio San Juan/Runoff", start=start_date, agg="mean")
```

### `read_csv`

Read a CSV file from a specified path. For now, this is limited to reading from the current network's file storage \(using AWS S3\), as viewable in the OpenAgua app.

Returns a [Pandas DataFrame](https://pandas.pydata.org/pandas-docs/version/0.23.4/generated/pandas.DataFrame.html) object.

{% hint style="info" %}
Since this function relies on Pandas read\_csv, you can prepare and test your function outside of OpenAgua with your Python programming environment of choice, using Pandas instead of OpenAgua.
{% endhint %}

#### Arguments

This function uses the [Pandas read\_csv](https://pandas.pydata.org/pandas-docs/version/0.23.3/generated/pandas.read_csv.html) function \(version 0.23.4\), and generally accepts the same arguments, which will be passed through directly. The `filepath_or_buffer` argument of the native Pandas read\_csv function should be replaced by the `path` argument. Some of the Pandas default argument values are over-ridden to accommodate the most typical CSV format, as shown in Example 1 below; these can still be changed in the function call. Arguments listed below include both over-ridden arguments and custom additional arguments.

| Argument | Data type | Description |
| :--- | :--- | :--- |
| `path` \(required\) | string | The path of the data of interest. |
| index\_col | integer or list | Pandas `index_col` argument. Default is `0`. |
| parse\_dates | boolean | Pandas `parse_dates` argument. Default is `True`. |
| flavor | string | The type of Python object to return. Options include `native` \(a Python dictionary\), `pandas`, and `json`. Note that this is not a Pandas `read_csv` argument. The default is `native`. |

#### Returns

A Python data object that depends on the `flavor` argument. The default is a native Python dictionary \(`flavor='native'`\).

#### Notes

For the time being, this must be called prepended with `self.` and with the last arguments as `**kwargs`, as in the examples below.

{% hint style="info" %}
CSV files loaded using `read_csv` are cached, so loading the same CSV file from different functions will _not_ significantly impact performance.
{% endhint %}

#### Examples

**Example 1**: Load inflow hydrology \(all at once\).

For this first example, let's assume we have a CSV file as follows:

```text
Date,Hetch Hetchy
2007-10-10,52.116
2007-10-20,96.703
2007-10-31,51.93
2007-11-10,87.213
2007-11-20,72.233
```

This can be loaded using the default arguments, as:

```python
self.read_csv("data/runoff.csv", **kwargs)
```

Since this function returns an entire time series \(as a Python dictionary object by default\), it will not be called again, as the data will already be readily available to the model. I.e., all data is loaded in one go. Note again that `return` is optional, so is omitted here.

**Example 2**: Load inflow hydrology \(per time step\).

```python
data = self.read_csv("data/runoff.csv", usecols=[0,1], **kwargs)
return data.iloc[timestep-1][1]
```

This example loads the dataset within the function, but since it returns only a single value, it will be called again every time step. This can be useful if some time-dependent manipulation of the data is needed, but is generally less efficient than the approach in Example 1. Not that this uses the built-in variable `timestep`. Since Python objects are indexed starting at zero, but `timestep` starts at 1, when using the [DataFrame iloc index method](https://pandas.pydata.org/pandas-docs/version/0.23.4/indexing.html), `timestep-1` must be used.

