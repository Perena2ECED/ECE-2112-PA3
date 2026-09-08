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

* The `cars.shape` returns a structural tuple describing the exact dimensions of the DataFrame. It outputs numbers structured in `(rows, columns), allowing to verify the structural size of the data set.

   ```
  cars.shape

  (32, 12)
  ```
* The `cars.iloc[5:10]`, stands for __integer location__, an integer position-based slicing to isolate specific conditions.
    * `5` --> It functions as the inclusive lower bound.  Since Python utilizes zero-based indexing, it prints out the 6th row of the data set.
    * `10` --> It functions as the exclusive upper bound, meaning the slice stops exactly before index 10. The boundaries successfully printed row           indices 5-9 to match the requested rows.

   ```
  cars_6_to_10 = cars.iloc[5:10] 
  cars_6_to_10

  This evaluates to the car model from the 6th to the 9th row, including all columns: mpg, cyl, disp, hp, drat, wt, qsec, vs, am, gear, and carb. 
  ```
* The `cars_6_to_10.loc[]` handles label-based selections across two dimensions separated by a comma.
  * The colon symbol `:` functions as an operator that instructs Pandas to retain the rows in the current slice.
  * The secondary list containing the collection of strings asks like `cars_6_to_10 = cars_6_to_10.loc[0:,`['Model', 'mpg', 'cyl', 'hp', 'gear']`]` functions as a column filter wherein the syntax only prints the request variables in that order.

  ```
  cars.loc[:,['Model']]

  This evaluates to the list of car models.
  ```

  ```
  cars_6_to_10 = cars_6_to_10.loc[0:,['Model', 'mpg', 'cyl', 'hp', 'gear']]
  cars_6_to_10

  This evaluates to the Model, mpg, cyl, hp, and gear of the car models.
  ```

# B. MODEL LOOKUP
The problem asks to display the complete row for the Toyota Corolla and only the model. mpg, hp, and wt for Pontiac Firebird without using hard-coded syntax.

* The inner syntax `cars['Model'] == 'Toyota Corolla' acts as a structural row-filtering Boolean mask. It evaluates each value in the `Model` variable column, filtering matches as `True` and mismatches as `False`. When it is placed inside the DataFrame subsetting bracket `cars[]`, it extracts only the elements that are true and stores them under the arbitrary variable `toyota`.

  ```
  toyota = cars[cars['Model'] == 'Toyota Corolla']
  toyota

      Model	          mpg	cyl	disp	hp	drat	 wt	 qsec	 vs	am	gear carb
  19	Toyota Corolla	33.9	4	71.1	65	4.22	1.835	19.9	1	 1	 4	  1
   ```

* The syntax ` pontiac = cars.loc[(cars['Model']=='Pontiac Firebird'), ['Model', 'mpg', 'hp', 'wt']]`, is a criterion used to locate specific points in the dataset, extracting relevant cells, and storing it to a new variable  `pontiac`.
    * `cars.loc` --> The property that the process handles axis selection across two distinct dimensions separated by a comma.
    * `cars['Model'] == 'Pontiac Firebird'` -->  The first dimension, performs a conditional string-matching check on the `Model` feature to                 automatically locate the precise observation row index.
    * `['Model', 'mpg', 'hp', 'wt'] --> This is an ordered array list of strings to define a selection boundary across the horizontal axis of the           DataFrame. It asks the system to extract unlisted data properties and only assigns the ask values to the four designated column labels.
  
  ```
  pontiac = cars.loc[(cars['Model']=='Pontiac Firebird'), ['Model', 'mpg', 'hp', 'wt']]
  pontiac

            Model	      mpg	  hp	  wt
  24	Pontiac Firebird	19.2	175	3.845
  ```

# C. MULTI-MODEL SUBSETTING
The problem asks to display data stored under selected_cars for the models: Datsun 710, Lotus Europa, and Ferrari Dino, keeping their records for Model, mpg, cyl, hp, and gear, but using their model values and displaying their shape.

* The `selected_cars = cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa')|(cars['Model']=='Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']]` functions to isolate rows simultaenously and saving it to the the variable selected_cars.
  * `selected_cars =cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa')|(cars['Model']=='Ferrari Dino')` --> It functions as a multi-conditional string using OR operator, `|` to automatically locate the precise observation row indices fpr the three car mode;s. IT stacks specific target positions into a single Boolean mask without relying on hard-coded row placements.
  * `['Model', 'mpg', 'hp', 'wt']]` --> It acts as a column filter using an ordered list of string materials. It instructs the indexing system to truncate the dataset's horizontal width, extracting only the five requested variable columns.

   ```
   selected_cars =cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa')|(cars['Model']=='Ferrari Dino'), ['Model', 'mpg', 'cyl',       'hp', 'gear']] 
  selected_cars

         Model	    mpg	 cyl hp	gear
  2	  Datsun 710	  22.8	4	 93	  4
  27	Lotus Europa	30.4	4	 113	5
  29	Ferrari Dino	19.7	6	 175	5
   ```
* The `selected_cars.shape reads the dimensional layout parameters of the targeted subset DataFrame. It outputs an execution tuple formatted in (rows, columns) to verify that the extracted object strictly follows the required dimensions.

   ```
   selected_cars.shape

   (3, 5)
   ```
# Version History

* 

