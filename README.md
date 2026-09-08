# ECE2112_PA3
Written and made by Steven Andrew A. Cruz of 2ECE-D

#EXPERIMENT 3: PYTHON DATA ANALYSIS (PANDAS)
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


```python
cars.shape

column_names= cars.columns.tolist()
column_names
```

```python
cars_6_to_10 = cars.iloc[5:10]
cars_6_to_10
```

```python
selectedcolumns = cars_6_to_10.loc[:,['Model', 'mpg', 'cyl','hp','gear']]
selectedcolumns
```



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

```python
pontiac = cars.loc[cars['Model']=='Pontiac Firebird',['Model','mpg','hp','wt']]
pontiac
```


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

```python
selected_cars.shape
```














