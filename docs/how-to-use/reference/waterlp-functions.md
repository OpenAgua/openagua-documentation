---
description: >-
  This serves as a temporary reference for functions available with OpenAgua's
  default water simulation model. This will move to a new dedicated site in the
  future.
---

# WaterLP functions

The following functions are available for use within the default OpenAgua model, WaterLP. See also the \[code repository for WaterLP\]\([https://github.com/openagua/waterlp-pywr](https://github.com/openagua/waterlp-pywr)\).

### get

Get data from another variable, or another time step, possibly aggregated.

```python
get("Monterrey/node/El Cuchillo/Storage", offset=-1)
```

| Argument | Data type | Description |
| :--- | :--- | :--- |
| offset | integer | Get a value from a specific time step offset. E.g., `offset=-1` returns the value from the last time step. |
| start | date string  or Pendulum date | This indicates that the value should be aggregated from more than one time step, with start indicating the start date of the aggregation period. The value should be either a [Pendulum](https://pendulum.eustace.io/) date object or a string \(e.g., `1999-10-01`\) that Pendulum can properly parse. |
| end | date string or Pendulum date | If aggregating a value, the end date of the aggregation period. The value should be either a [Pendulum](https://pendulum.eustace.io/) date object or a string that Pendulum can properly parse. If the end date should be the current date, this can be omitted. |
| agg | string | If aggregating a value \(i.e., with `start` and/or `end)`, this indicates how the value should be aggregated. Options include `mean` and `sum`. Default is `sum`. |

### read\_csv

