# ECE-2112-PA3

Paulene Anne V. Pereña <br>
2ECE-D

This repository contains the Programming Assignment 3 for the course Advanced Computer Programming (ECE2112).
This project consists of three Python problems assigned to __Experiment 3: Python Data Analysis (PANDAS).__


* The statement `import pandas as pd` loads an external data library into the environment. The `pd` creates a shortened  namespace handle to lessen typing time.
* The function `pd.read_csv("file name")` is used to load a comma-separated values file that automatically converts it into rows and columns into a structured class known as `pd.DataFrame`, which holds a two-dimensional data structure that holds heterogeneous data types.

  ```
  cars = pd.read_csv('cars.csv')
  cars

  This evaluates to the data frame cars.csv that was asked for.
  ```
 
  ```
  cars = pd.DataFrame(cars)
  cars

  This evaluates to the two-dimensional DataFrame created for the csv.
  ```
  

# A. POSITIONAL AND LABEL-BASED SLICING
  The problem asks to display the shape and the complete list of column names of cars using positional slicing with the arbitrary variable               cars_6_to_10, isolating rows 6 to 10, which displays only the columns Models, mpg, cyl, hp, and gear, while utilizing iloc and column labels.

* The `cars.shape` shows a structural tuple describing the exact dimensions of the DataFrame. It outputs numbers structured in `(rows, columns), allowing to verify the structural size of the data set.

   ```
  cars.shape

  (32, 12)
  ```
* The `cars.iloc[5:10]`, stands for integer location, an integer position-based slicing to isolate specific conditions.
    * `5` --> It functions as the inclusive lower bound.  Since Python utilizes zero-based indexing, it prints out the 6th row of the data set.
    * `10` --> It functions as the exclusive upper bound, meaning the slice stops exactly before index 10. The boundaries successfully printed row           indices 5-9 to match the requested rows.

   ```
  cars_6_to_10 = cars.iloc[5:10] 
  cars_6_to_10

  This evaluates to the car model from the 6th to the 9th row, including all columns: mpg, cyl, disp, hp, drat, wt, qsec, vs, am, gear, and carb. 
  ```
* The `cars_6_to_10.loc[]` handles label-based selections across two dimensions separated by a comma. The colon symbol `:` functions as an operator that instructs Pandas to retain the rows in the current slice. The secondary list containing the collection of strings asks like cars_6_to_10 = cars_6_to_10.loc[0:,`['Model', 'mpg', 'cyl', 'hp', 'gear']`] functions as a column filter wherein the syntax only prints the request variables in that order.

  ```
  cars.loc[:,['Model']]

  This evaluates to the list of car models.
  ```

  ```
  cars_6_to_10 = cars_6_to_10.loc[0:,['Model', 'mpg', 'cyl', 'hp', 'gear']]
  cars_6_to_10

  This evaluates to the Model, mpg, cyl, hp, and gear of the car models.
  ```

B. 
