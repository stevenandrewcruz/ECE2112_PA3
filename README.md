# ECE2112_PA3
Written and made by Steven Andrew A. Cruz of 2ECE-D

# EXPERIMENT 3: PYTHON DATA ANALYSIS (PANDAS)
The topic of this experiment is all about PANDAS or Python Data Analysis. The main focus of this experiment is to load a CSV dataset into a Pandas DataFrame, to be able to select rows and columns using positional label-based indexing, to filter records using conditions on a DataFrame column; and finally extract a well-defined subset of data without changing the source data.  



# A. POSITIONAL LABEL-BASED SLICING 
After loading cars, complete the following operations.
a. Display the shape and complete list of column names of cars.
b. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where
the first data row is row 1.
c. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.
Requirement: The row selection in part (b) must use iloc; the column selection in part (c) must
use column labels.

METHODS USED:

 ```python
cars=pd.read_csv('cars.csv')
cars
```
To load the file `cars.csv` the function `cars = pd.read_csv('cars.csv')` is used and stored in `cars`. The resulting output is the full list in the file with complete columns and rows. Note that this function specifically calls in csv files in the same file where the code is saved in. 

```python
cars.shape
(32, 12)

column_names= cars.columns.tolist()
column_names

['Model',
 'mpg',
 'cyl',
 'disp',
 'hp',
 'drat',
 'wt',
 'qsec',
 'vs',
 'am',
 'gear',
 'carb']

```
The function `cars.shape` is used to show the dimension of the list which would result in an output of `(32,12)`. The function `column_names = cars.columns.tolist()` generates a list of the column names from the file and stored in `columns_names`. 

```python
cars_6_to_10 = cars.iloc[5:10]
cars_6_to_10

```
The function `cars_6_to_10 = cars.iloc[5:10]` is used to display contents of row 6 to 10 only from the dataset with their complete column data and stored in `cars_6_to_10`. The function uses a positional slicing method in order to attain the dataset by setting a parameter such as `[5:10]` as they are rows 6 to 10 and calling their data row.  


```python
selectedcolumns = cars_6_to_10.loc[:,['Model', 'mpg', 'cyl','hp','gear']]
selectedcolumns
```
The function `selectedcolumns = cars_6_to_10.loc[:,['Model', 'mpg', 'cyl','hp','gear']]` is used to call in the same rows, but only calling specific column names and their respective model values. This portion of the function `.loc[:,['Model', 'mpg', 'cyl','hp','gear']]` locates the specific column names and respective model values with `[:,[` being left empty since the required parameter has already been met for the data row. The output has the same rows as the previous function but only have the specified model values and column names which are `['Model', 'mpg', 'cyl','hp','gear']`. This is stored in `selectedcolumns`. 


# B. MODEL LOOKUP 
Use Boolean indexing on the Model column to answer both requests.
a. Display the complete row for Toyota Corolla.
b. For Pontiac Firebird, display only Model, mpg, hp, and wt.
Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to
locate either model.

METHODS USED:

```python
toyota = cars.loc[cars['Model']=='Toyota Corolla']
toyota
```
The function `toyota = cars.loc[cars['Model']=='Toyota Corolla']` uses a boolean indexing method where it locates the specific model name of the car by looking at the data column `Model` to extract the required model alongside its complete model values. The output is 1 row with the required model name and its complete model values and column names. The data is stored in `toyota`. 

```python
pontiac = cars.loc[cars['Model']=='Pontiac Firebird',['Model','mpg','hp','wt']]
pontiac
```
The function `pontiac = cars.loc[cars['Model']=='Pontiac Firebird',['Model','mpg','hp','wt']]` uses a boolean indexing method where it locates the specific model name of the car by looking at the data column `Model` and calling specific column names and their respective model values. The output is 1 row with the required model name and its specific model values which are `['Model','mpg','hp','wt']`. The data is stored in `pontiac`. 


# C. MULTI-MODEL SUBSETTING 
Create a DataFrame named selected cars containing only the records for three models: Datsun 710,
Lotus Europa, and Ferrari Dino. For these records, retain only Model, mpg, cyl, hp, and gear. Select the rows by their model values rather than by row numbers. Display selected cars and its shape.
Required check: The final DataFrame must contain exactly three rows and five columns.


METHODS USED:

```python
selected_cars = cars.loc[(cars['Model']=='Datsun 710')|
    (cars['Model']=='Lotus Europa')|(cars['Model']=='Ferrari Dino'),
    ['Model','mpg','cyl','hp','gear']]
selected_cars
```
The function `selected_cars = cars.loc[(cars['Model']=='Datsun 710')|(cars['Model']=='Lotus Europa')|(cars['Model']=='Ferrari Dino'),['Model','mpg','cyl','hp','gear']]` essentially calls in multiple car models by their model values `['Model','mpg','cyl','hp','gear']`. This code was possible by chaining together the model cars with an `|` operator linking them to the specified model values and column names. The output has 3 rows with the specified column names and their respective model values. 

```python
selected_cars.shape
(3, 5)
```
This functions shows the dimension of the the previous output. The result is `(3, 5)` 

# README FILE HISTORY:
September 8 2026 Creation of repository 
September 8 2026 Uploading of files 
September 8 2026 Readme file layout 
September 10 2026 Finalizing of readme file 
September 10 2026 Minor editing for Readme File 











