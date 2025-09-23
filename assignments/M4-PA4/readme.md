 # ✏️PA4 - Readme✏️

This folder contains all the files required for the second programming assignment, for the topic Python Data Analysis.

## Intended Learning Outcomes:
    1. To identify the codes and functions needed in cleaning and visualizing data
    2. To be able to apply and use the different codes and functions in creating a Python program that will be used in data wrangling and data visualization
    
# 📄Problems Contained📄
All the problems contained in this files are:
1. ECE BOARD EXAM PROBLEM::
- First, for both problems we will be loading in our CSV file as a PANDAS DataFrame, so firstly I imported PANDAS as pd and used the pd.read.csv() function to load the provided csv file. I also loaded the Numpy and Matlab libraries for later.
```
    # Library Import

    import numpy as np # Importing numpy library
    import pandas as pd # Importing pandas library
    import matplotlib.pyplot as plt # Importing plotting/visualization library
```
```
    # Read from file Snippet
    df = pd.read_excel('board2.xlsx')
    df # Display unaltered file
```
-  For Problem 1 - Data frame 1, I simply used the .loc function to our initial data set to splice a specific subset of the df data frame. To create our splicing parameters, we use the & or and sign to combine multiple parameter checks. So simply we test for all entries with hometowns in Visayas AND their grades are less than 70 in Math. Finally, we simply format the final table according to the sample output and display it.
```
    # Data Frame 1 Snippet
    Vis = df.loc[(df['Hometown'] == 'Visayas') & # Using splicing, find all entries where hometown is Visayas.
                (df['Math'] < 70) # Using & (AND), additionally find only entries with Math grade less than 70.
                , ['Name', 'Gender', 'Track', 'Math']] # Formatting options to match sample output.

    Vis # Display first Data Frame
```
-  For Problem 1 - Data frame 2, I used the same structure again. We splice by checking for the track, hometown, and grade of electronics as required by the problem description. Then we simply format again and store the data frame in Instru and display the table.
```
    # Data Frame 2 Snippet
    Instru = df.loc[(df['Track'] == 'Instrumentation') & # Test for entries where Track is Instrumentation.
             (df['Hometown'] == 'Luzon') & # Using & (AND), additionally test for entries where Hometown is Luzon.
             (df['Electronics'] > 70) # # Finally, using & (AND), additionally test for entries where the Electronics grade is greater than 70.
             , ['Name', 'GEAS', 'Electronics']] # Formatting options to match sample output.

    Instru # Display second Data Frame
```
-  Finally, for Problem 1 - Data frame 3, We have to intreoduce a new category that is not in the original data set. Because of this, I generally opt to copy the original data frame and modify it to add the average column as opposed to directly adding it to the original data set. Once I have copied the data frame, we can create the average column by using the .mean Pandas function with the axis set to one to get the average according to the vertical (column) of each grade. Once we've added the average column to our dataframe, we can simply use .loc to splice data according to the problem description, which is searching for Female students from Mindanao with an average grade greater than 55. We apply formatting once again and then display the problem.
```
    # Data Frame 3 Snippet
    Mindy = df.copy() # Create a copy of the base DataFrame to avoid creating columns that do not exist in the original data set.
    Mindy['Average'] = df[['Math','Electronics','GEAS','Communication']].mean(axis=1) # Create an average column using the Pandas function .mean with the axis set to one.

    Mindy = Mindy.loc[(Mindy['Gender'] == 'Female') & # Test for entries where Gender is Female.
                (Mindy['Hometown'] == 'Mindanao') & # Using & (AND), additionally test for entries where Hometown is Mindanao.
                (Mindy['Average'] > 55) # Finally, using & (AND), additionally check for the entries where average grade is greater than 55. 
                , ['Name', 'Track', 'Electronics', 'Average']] # Formatting options to match sample output.

    Mindy # Display third Data Frame
```
2. PROBLEM 2
-  Problem 2 is quite a bit trickier, I initially wanted to use a pairplot graph but I was under the impression that I would have to complete the PA4 before the 1 hour 30 minute time limit so in my haste I opted for a bar graph with minimal design. However, in future versions I will most likely opt into using a pairplot instead of a bar graph. Either way, the first step for the problem was again copying from the original df data frame to avoid editing the original and adding the average just as we did before.
```
    # Copy Snippet
    V = df.copy() # Create a copy of the base DataFrame to avoid creating columns that do not exist in the original data set.
    V['Average'] = df[['Math','Electronics','GEAS','Communication']].mean(axis=1) # Create an average column using the Numpy function .mean with the axis set to one.
```
- However, the problem requires us to find a correlation between the features of Gender, Track, and Hometown to the students final grade. Doing a cursory search on the internet and through our cheat sheets led me to the Pandas documentation website:

https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.apply.html
https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.factorize.html#pandas.factorize
https://pandas.pydata.org/docs/dev/reference/api/pandas.DataFrame.corrwith.html#pandas.DataFrame.corrwith

- Through these resources I opted to create a Pearson's correlation value for each of the categories using the .corrwith function. However, I initially ran into issues as the values were not intgers. This is where I learned the .apply function in the cheat sheets and the factorize function in the Pandas documentation, which converts non-integer values into indexed values that can be used with the .corrwith function. Once I had my correlation values I simply displayed the function for us to get a better understanding of what the correlation values are and what values are attached to them.
```
    # Getting correlation values:
    Cor = V[['Gender', 'Track', 'Hometown']].apply(lambda x: pd.factorize(x)[0]).corrwith(V['Average'])

    # Breakdown:
        # V[['Gender', 'Track', 'Hometown']] -  Select only the focus features (Gender, Track, Hometown)
        # .apply(lambda x: pd.factorize(x)[0]) - Since we're dealing with non-integer values in trying to construct a correlation table, 
        #                                        I decided on using the .apply function to utilize the lambda factorization on our values 
        #                                        to convert them into values that can be compatible with the corrwith Pandas function.
        # .corrwith(V['Average']) - The corrwith function in Pandas correlates one DataFrame to another, by placing V['Average'] we are 
        #                           comparing the entirety of the prior Data Frame with its function applied to the average only.

    Cor # Display test case
```
- Again as stated before, I opted to use a bar graph instead of the pairplot I wanted due to my percieved time restraints and so I simply made a new figure and a bar graph.
```
    # Figure Display Snippet
    plt.figure() # Create a new figure using Matplot lib.
    fig = plt.bar(Cor.index, Cor.values) # Create a bar graph to show correlation between all values.
```

# 📁Directory Navigation📁
The organization of this repository to get to this file is as follows:
```
└── 2112-advprog 📂
    └── assignments 📄
        ├── M2-PA3 🐍
            └── pa4.ipynb ⭐
            └── board2.xlsx 📄
            └── readme.md 📖
```

# ⬇️Download Instructions⬇️
Download or clone this repository to get the files. Then using either Jupyter notebook or through the Jupyter addon on Visual Studio Code, open the file and run the cells of concern.




