# Poetry Test Selection

The Pytest documentation introduces the ability to change both the files
searched for tests and the function names that are considered tests. The Pytest
default is to only look for tests inside `test_*.py` or `*_test.py` files, and
to look for function names prefixed with `test` inside those files. (Pytest also
looks for class names prefixed with `Test` but we will not cover those here).

This repository demonstrates how to choose alternate Pytest file and function
names when using Poetry. Following the suggestions
[here](https://docs.pytest.org/en/7.1.x/example/pythoncollection.html#customizing-test-collection),
we configure Poetry to search all python files for tests. Using the example
[here](https://docs.pytest.org/en/7.1.x/example/pythoncollection.html#changing-naming-conventions)
we consider a test function to be one with a name ending in `_check`. The parts
of the `pytest.ini` file that produce these effects for Pytest look like this:

```
python_files = *.py  # Discover tests in every python file
# Only consider a function to be a test if it ends with '_check'
python_functions = *_check
```

There are two different test setups in this repository. To see the successful
examples, move to the `succeed` directory and run both `pytest` and `TBD`. To see the failing examples, move to the `fail` directory and run the
same commands.
