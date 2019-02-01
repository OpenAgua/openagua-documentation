# Getting started

## Data input

Data may be input either directly in the form of fundamental data types of _time series_, _array_, _scalar_, or _descriptor_ \(text\), or indirectly via Python-based functions.

## Functions

Data input as a code-based script are evaluated as functions either once at the beginning of a model run, or on a per-time step basis, depending on whether the fundamental variable data type is fixed \(array, scalar, or descriptor\) or temporally variable \(time series\), respectively.

The Python-based scheme enables the user to import data, enter custom functions directly into the code, etc. The most important principles to understand when entering functions are described below, though a full description of the Python programming language is beyond the scope of this documentation.

### Returning a value

Let's start with two very simple functions:

```python
5
```

and

```python
return 5
```

Both of these result in a value of `5` every time step \(assuming this function is for a time series\). The code evaluator needs to know which value the code should return. In general, this is achieved with the `return` statement. However, the evaluator will automatically add `return` if it is missing, so that if the value to be returned is on the last line, then no `return` statement is needed.

In many cases, including `return` is simply a matter of personal preference. But this is particularly useful if a return is nested in the last part of a conditional statement. To demonstrate, the following three versions of code input yield the exact same result when evaluated:

```python
if date.month in [6,7,8]:
    x = 0.5
else:
    x = 1
x
```

```python
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

In the first case, because `x` is on the last line, `return` is not needed; `x` will be the value returned. In the second two cases, values are returned explicitly. As a side note, Python can be quite succinct at times, allowing the above to be written, for example, as:

```python
0.5 if date.month in [6,7,8] else 1
```

The last few examples above should raise a question: where does `date` come from? WaterLP contains several convenient built-in variables, as described in the next section.

