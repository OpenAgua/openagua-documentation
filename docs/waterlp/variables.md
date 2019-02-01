OpenAgua includes a growing list of built-in variables available for use in functions. As of writing, these include the following:

* `timestep` - An ordinal integer representing the current timestep (i.e., 1, 2, 3, ..., N).
* `date` - A the current timestep's date as a [Pendulum](https://pendulum.eustace.io) date object, which has numerous useful [attributes and properties] (https://pendulum.eustace.io/docs/#attributes-and-properties) (e.g., `date.month`, etc.).
* `periodic_timestep` - An ordinal integer representing the timestep in the current water year. For example, a monthly time step model starting in October would have `periodic_timestep` of 1, 2, 3, ..., 12, with 1 in October and 12 the following September. A daily time step model would similarly range from 1 to 365 (or 366 if leap years are considered).
* `water_year` - The current water year, which is defined by the calendar year of the *last month* in the water year. If it helps, here is the specific equation for `water_year`:
```python
water_year = date.year + (0 if date.month < self.start_date.month else 1)
```
where `self.start_date` is the start date of the model (don't worry if you don't understand the `self.` bit; this is for reference only). Speaking of start date...
* `start_date` and `end_date` - These are also [Pendulum](https://pendulum.eustace.io) date objects representing--you guessed it--the start date and end date, respectively, of the model.

This is a preliminary list, and will likely expand in the future as needs arise. Feel free to suggest something!