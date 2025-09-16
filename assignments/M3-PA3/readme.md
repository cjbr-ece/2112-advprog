 # ✏️PA3 - Readme✏️

This folder contains all the files required for the second programming assignment, for the topic Python Data Analysis.

## Intended Learning Outcomes:
    1. To identify the codes and functions incorporated in the Pandas library
    2. To be able to apply and use the different codes and functions in creating a Python program using a Pandas library
    
# 📄Problems Contained📄
All the problems contained in this files are:
1. PROBLEM 1:
- First, for both problems we will be loading in our CSV file as a PANDAS DataFrame, so firstly I imported PANDAS as pd and used the pd.read.csv() function to load the provided csv file.
```
    # Problem 1 - Loading from file
    # Library Import
    import pandas as pd

    # Importing from file Snippet
    cars = pd.read_csv('cars.csv') # Using the pd.read_csv function we can read our    csv file and convert it into a DataFrame and we can save it under the name cars.    
```
-  For part a, we can simply save to a new DataFrame called head and using the .head() function to get the first 5 entries.
```
    # Part A Snippet
    head = cars.head() # The head function simply retrieves the first 5 values, and we can save it to the name head
    head # Display of test case
```
- Similarly, we can simply save to another DataFrame named tail and use the .tail() function to get the last 5 entries.
```
    # Part B Snippet
    tail = cars.tail() # The tail function simply retrieves the last 5 values, and we can save it to the name tail
    tail # Display of test case
```
- Finally, I decided to export all the DataFrames back out labeled with head_ and tail_.
```
    # Exporting to file Snippet
    head.to_csv('head_Rivera_Pandas-P1.csv')
    tail.to_csv('tail_Rivera_Pandas-P1.csv')
```

2. PROBLEM 2
- For the second problem, we once again import and read like in problem 1. Once we have them we can deal with the first case.
```
    # Problem 2 - Subsetting, slicing, indexing
    # Library Import
    import pandas as pd

    # Importing from file Snippet
    cars = pd.read_csv('cars.csv') # Using the pd.read_csv function we can read our    csv file and convert it into a DataFrame and we can save it under the name cars.    
```
- For part a, we can simply use .iloc() and use slices to indicate our m and n values in the iloc. Since we need the first 5 columns, we can simply use 0:5 to get the values from index 0 to 5. As for the odd values part, we can simply use a slice of ::2 which basically means to scan the whole DataFrame using 2 as an increment, effectively skipping all even numbered columns.
```
    # Part A Snippet
    a = cars.iloc[0:5, ::2] # .iloc - gets the value with m row, n column, we simply slice 0:5 which gets only the columns index 0 to 5.
                            # Next, we use indexing again in the column field but we sinply use ::2 which translates to for the entire DataFrame, 
                            # but incrementing using 2 to only get the odd numbered values.
    a # Display test case
```
- For part b, we can simply index using .loc searching for any element that equates to 'Mazda RX4' under the column labeled 'Model' in the cars table.
```
    # Part B Snippet
    b = cars.loc[cars['Model'] == 'Mazda RX4'] # We simply use indexing using .loc function with the paramaters of testing all elements of the value column to the target value.
    b # Display test case
```
- For part c, we can use indexing again using loc but we have to display specific columns only. We can simply format the output using the specifiers at the end of ['Model', 'cyl'].
```
    # Part C Snippet
    c = cars.loc[cars['Model'] == 'Camaro Z28', ['Model', 'cyl']] # We use indexing again just like the example above, but we simply only include the model and cylinder count by adding the formatting segment.
    c # Display test case
```
- Finally, for part d we simply use indexing one last time, however we have to use the '|' symbol which in PANDAS is read as 'or' which parallels the behavior of the or function in Python. This allows us to test for multiple cases in one singular .loc function. Once we have our values, we can simply format using specifiers once again.
```
    # Part D Snippet
    d = cars.loc[(cars['Model'] == 'Mazda RX4 Wag') |
                (cars['Model'] == 'Ford Pantera L') |
                (cars['Model'] == 'Honda Civic')
            , ['Model', 'cyl', 'gear']] # Using indexing again, we simply use the 'or' symbol | for Pandas to test for multiple values. 
                                        # Once we have them, we simply use the same formatting elements as above but including the gear.
    d # Display test case
```

# 📁Directory Navigation📁
The organization of this repository to get to this file is as follows:
```
└── 2112-advprog 📂
    └── assignments 📄
        ├── M2-PA3 🐍
            └── Rivera_Pandas-P1.ipynb ⭐
            └── Rivera_Pandas-P1.py ⭐
            └── Rivera_Pandas-P2.ipynb ⭐
            └── Rivera_Pandas-P2.ipynb ⭐
            └── head_Rivera_Pandas-P1.csv 📄
            └── tail_Rivera_Pandas-P1.csv 📄
            └── a_Rivera_Pandas-P2.csv 📄
            └── b_Rivera_Pandas-P2.csv 📄
            └── c_Rivera_Pandas-P2.csv 📄
            └── d_Rivera_Pandas-P2.csv 📄
            └── readme.md 📖
```

# ⬇️Download Instructions⬇️
Download or clone this repository to get the files. Then using either Jupyter notebook or through the Jupyter addon on Visual Studio Code, open the file and run the cells of concern.



