# Silent Error in R Data Frame Subsetting

This repository demonstrates a subtle bug in R related to data frame subsetting when using character vectors to specify column names.  If the character vector includes a name that does not exist in the data frame, R silently ignores it rather than throwing an error, potentially leading to unexpected results and difficult-to-debug issues.

## The Bug

The `bug.R` file contains code that attempts to subset a data frame using a character vector. One of the names in the character vector ("D") is not a valid column name in the data frame.  Instead of reporting an error, R proceeds without warning, resulting in a subset with only columns A and C.

## The Solution

The `bugSolution.R` file demonstrates how to address this issue using the `%in%` operator to check if column names are valid before subsetting, ensuring that the code behaves as expected and notifies the user of invalid column names.