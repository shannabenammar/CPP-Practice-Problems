# Lab 1.2 - Processing a List of Names

Write a C++ program to do the following:
- Load up an array of names from the files `names.data`
    - Assigns integer id's to each name, starting at 1001, and in the order in which they are read from the file (so the first name would be assigned 1001, the second 1002, etc)
        - We don't have classes yet, so use *parallel arrays*, i.e., two arrays of the same capacity, the first containing the names, the second the corresponding id
- Sort the arrays by name
- Write the sorted data to the file `results.data`, each name / id pair on a separate line

**Notes**

- Assume no more than 50 names; make sure you perform capacity checking
- Don't forget to check for a successful file open
- Use exception handling for the errors (no file, and capacity exceeded)
- Use *procedural decomposition*: `load`, `sort`, `writeToFile` functions
    - how about a `swap` function for use by the sort?

## Sample Test Run #1

For example if the file `names.data` contains:

```
Langsam
Tenenbaum
Arnow
Weiss
Cox
```

upon program termination, the console output should be:

```
5 records processed
```

the file `results.data` should contain:

```
Arnow 1003
Cox 1005
Langsam 1001
Tenenbaum 1002
Weiss 1004
```

and the exit code should be 0.

## Sample Test Run #2

If the file `names.data` did not exist, the console output should be:

```
*** Exception *** input file names.data not found
```

and the exit code should be 1.

## Sample Test Run #3

If the file `names.data` contains more than 50 names, the console output should be:

```
*** Exception *** array capacity exceeded
```

and the exit code should be 1.