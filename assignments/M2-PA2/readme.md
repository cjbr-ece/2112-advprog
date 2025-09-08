
# Project Title

A brief description of what this project does and who it's for

 # ✏️PA2 - Readme✏️

This folder contains all the files required for the second programming assignment, for the topic Numerical Python.

## Intended Learning Outcomes:
    1. To identify the codes and functions incorporated in the Numpy library
    2. To be able to apply and use the different codes and functions in creating a Python program using a Numpy library
    
# 📄Problems Contained📄
All the problems contained in this files are:
1. NORMALIZATION PROBLEM:
- For the first problem , I had to first create a 5x5 np.array that was full of random values.
```
    # Initial Variable Declaration Snippet
    X = np.random.random((5,5)) # Using the variable given in the experiment sheet.
```
- I opted to create a function for the normalization, as I want to practice making modular pieces of my program as I think it'll be useful later down the line. Creating the function, I simply used the .mean() and .std() functions to get the mean and standard deviation of my randomly generated array and plugged the values into the formula for solving for Z-deviation score. As NumPy broadcasts the operation through the entire array, I simply save it as a new array z, in case I ever need to access the original array in a different application. I opted to build in the saving into the normalization function but it can also be removed for specific use cases.
```
    # Normalization Code Snippet
    def normalize(x): # I decided on creating a function because modularity is a general coding principle.
        z = (x - x.mean()) / x.std() # Translating, this is simply the formula Z = X - xbar / omega.
        np.save('X_normalized.npy', z) # Saving to the file name as required by the problem.
```
Once that was done I simply used the normalize function and loaded the file for the print case.
```
    # Print Snippet
    normalize(X) # Test Case
    print(np.load('X_normalized.npy')) # Print to simply see the saved file using np.load.
```
2. DIVISIBLE BY 3 PROBLEM
- For this problem, I had a little trouble figuring out how to fill my array with the squares of from 1-100. Remembering that the range is exclusive or does not include the range value in its creation helped me figure it out. After I figured out how to fill in the array, reshaping it into the needed 10x10 array shape was simple by using the built in np.reshape() function.
```
    # Initial Variable Declaration
    A = np.arange(1,101) ** 2 # First I create the array of squares from 1-1001 because its non inclusive.
    A = A.reshape(10,10) # Then, using the reshape function of np.arrays, I reshape the function to 10x10.
```

- As for creating the array full of entries that were divisible by 3, I simply used the format for indexing to search for all the variables encased in the array that when divided by 3 left no remainder, confirming its divisibility by 3. I stored it in a seperate np.array in case the original is to be used for something else. After that, I simply saved the new array according to the file format requested.
```
    # Finding values divisible by 3
    B = A[A % 3 == 0] # Using indexing, we can search for all values of A that are divisible by 3 and have no remainder using modulo division.
    np.save('div_by_3.npy', B) # Saving to the file name as required by the problem.
```
Once that was done I simply loaded the file for the print case.
```
    # Print Snippet
    print(np.load('div_by_3.npy')) # Test Case 1, Printing B for review.
```

# 📁Directory Navigation📁
The organization of this repository to get to this file is as follows:
```
└── 2112-advprog 📂
    └── assignments 📄
        ├── M2-PA2 🐍
            └── pa2.ipynb ⭐
            └── X_normalized.npy 📄
            └── div_by_3.npy 📄
            └── readme.md 📖
```

# ⬇️Download Instructions⬇️
Download or clone this repository to get the files. Then using either Jupyter notebook or through the Jupyter addon on Visual Studio Code, open the file and run the cells of concern.

