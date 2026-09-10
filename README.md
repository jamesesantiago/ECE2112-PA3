# ECE2112-PA3

**By: James Eon M. Santiago | 2ECE-B**


This Repository Contains the Programming Assignment #3 for the Course "Advanced Computer Programming and Algorithms", which includes three python problems related to Module 3 - Numpy and Pandas.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# **(A) Positional and Label-Based Slicing**

Display the shape and complete list of column names of cars. Using positional slicing, create cars 6 to 10 containing rows 6 through 10 of the dataset, where the first data row is row 1. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

We must first add ```import pandas as pd``` for us to manipulate the data provided which is ```cars.csv```. We also need to add a ```pd.read_csv()``` function to allow us to read the file.

```python
import pandas as pd
cars = pd.read_csv("cars.csv")
```

To display the cars, we add ```cars``` and ```cars.shape``` to display the number of rows and columns in the given data.

```python
cars
cars.shape
```

The function ```.iloc()``` allows us to slice a portion of the data entry through the means of integer position.

```python
cars_6_to_10 = cars.iloc[6:11]
cars_6_to_10
```

The function ```.loc``` on the other hand allows us to slice the portion of the data based on the labels of the entries.

```python
cars_6_to_10.loc[:,['Model','mpg','cyl','hp','gear']]
```

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# **(B) Model Lookup**

Use Boolean indexing on the Model column to answer both requests. Display the complete row for Toyota Corolla. For Pontiac Firebird, display only Model, mpg, hp, and wt. Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to
locate either model.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Boolean Indexing - Is a method of using conditions, using true or false values to filter out exactly what is needed from a given entry. In this case we need our Model to be a Toyota Corolla. So we put ```cars[Model] == 'Toyota Corolla'``` 

```python
toyota = cars.loc[cars['Model'] == 'Toyota Corolla']
toyota
```

The function ```.loc``` is used in this case to find the Model Pontiac Firebird, and display its Model, mpg, hp, and wt only. 

```python
pontiac = cars.loc[cars['Model'] == 'Pontiac Firebird',['Model','mpg','hp','wt']]
pontiac
```

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# **(C) Multi-Model Subsetting**

Create a DataFrame named selected cars containing only the records for three models: Datsun 710,Lotus Europa, and Ferrari Dino. For these records, retain only Model, mpg, cyl, hp, and gear. Select the rows by their model values rather than by row numbers. Display selected cars and its shape.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The ```pd.DataFrame()``` Is a panda function that allows us to read a given data in DataFrame form.

The ```.loc``` function is used here to locate the specified models while also filtering out the only required columns.

The Boolean | or OR operator is used to combine conditions, allowing the DataFrame to include the rows when at least one of the conditions are true.

The ```.shape``` function is used to display the number of rows and columns there are in the DataFrame.

```python
selected_cars = pd.DataFrame(cars.loc[(cars['Model'] == 'Datsun 710') | (cars['Model'] == 'Lotus Europa') | (cars['Model'] == 'Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']])
selected_cars
```

```python
selected_cars.shape
```

# **Thank you for reading!!** 
