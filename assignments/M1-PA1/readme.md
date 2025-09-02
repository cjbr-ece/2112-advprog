# ✏️PA1 - Readme✏️

This folder contains all the files required for the first programming assignment, for the topic Introduction to Python Programming.

## Intended Learning Outcomes:
```
1. To identify the basic codes and functions in Python Programming
2. To be able to apply the different codes and functions in creating a Python program,
```
# 📄Problems Contained📄

All the problems contained in this files are:
1. ALPHABET SOUP PROBLEM
- This problem requires the program to arrange a given string in alphabetical order. For this particular application, I decided to use the sort function built into Python, however that would require me to first convert the my string into a list.

        
            # Conversion Code Snippet
            listS = list(strS) # This is converting our string strS to a list labeled listS.
            listS.sort() # This uses the sort function of a list to sort the letters alphabetically.

- Once I was able to sort the list, the next part of the problem would require me to reconvert the now sorted list back into a string. For this application, I decided on using a repetition structure to add each letter in the list to the original string value after resetting it.

            # Print Code Snippet
            strS = '' # By resetting the original string, we can set the new string in its place.
            
            for x in listS: # Repetition structure for every object in the list.
                strS += x # Simply add each letter from the list to our string.
                
            print(strS) # This is simply to see that the string has been changed.

2. EMOTICON PROBLEM
- For the emoticon problem, creating a function using if statements searching for the required values using the in function in Python would be quite simple, however I realised that if the word would have a different uppercase/lowercase combination of characters, the code would then stop working. I had some options built into Python but I opted to use exclusively string modifications taught in the first module.
        
            # Admittedly Overcomplicated Conversion Code Snippet
            # Case 1 - Smile
            if "smile" in strS.lower():    # Search for the required string
                strS = strS[0:strS.lower().find("smile"):1] + strS.lower()[strS.lower().find("smile"):len(strS):1].replace("smile", ":)"
        
- So a quick explanation for whats happening in the snippet, essentially using the find() attribute in strings, I can find where specifically a search term starts and stops and using that information to change the case of only the required string in order to accept different uppercase/lowercase combinations of the search string, in this case smile, using the slice function and simply adding the lowercase part to the end of the returned string.

- Admittedly the only downside to this implementation is the rest of the string becomes lower case, but given the examples cases given it's a solution I'm willing to use since I was more concerened over different cases not being recognized.

- After that I simply reused the same code snippet for the rest of the cases in an elif structure:
            
            # Case 2 - Grin
            elif "grin" in strS.lower():    # Search for the required string
                strS = strS[0:strS.lower().find("grin"):1] + strS.lower()[strS.lower().find("grin"):len(strS):1].replace("grin", ":D") # Search code.
            # Case 3 - Sad 
            elif "sad" in strS.lower():    # Search for the required string
                strS = strS[0:strS.lower().find("sad"):1] + strS.lower()[strS.lower().find("sad"):len(strS):1].replace("sad", ":((") # Search code.
            # Case 4 - Mad
            elif "mad" in strS.lower():    # Search for the required string
                strS = strS[0:strS.lower().find("mad"):1] + strS.lower()[strS.lower().find("mad"):len(strS):1].replace("mad", ">:(") # Search code.
            
- Then finally, I simply print the output string.
            
            print(strS) # Finally, output the string so you can see if it worked.

3. UNPACKING LIST PROBLEM
- Finally, the final problem is quite simple. For the first part which requires the first value of the list, I simply called the first variable based on the index as shown below:

            first = listL[0] # Simply enough, the first index of a list will always be index 0, so we can simply get it as so.

- Same can be done for the next part, which is getting the last value of the list using the index by getting the length of the list and substracting by 1 to get the value starting from 0 as opposed to 1.

            last = listL[len(listL) - 1] # Conversely, whatever the last in an index will be equal to the length of the list, so we can use len().

- As for the portion for getting the rest of the list, we can simpy slice the list from index 1 to the index of the end of the list - 1.

            middle = listL[1:len(listL) - 1] # As for the middle, we can just use the list function to get the index 1 up till second to last.

- Finally, to complete the function, we simply print using the format provided:

            print("First:", first, "Middle:", middle, "Last:", last) # Finally, output the list according to our problem instructions.
            
# 📁Directory Navigation📁

The organization of this repository to get to this file is as follows:
```
└── 2112-advprog 📂
    └── assignments 📄
        ├── M1-PA1 🐍
            └── pa1.ipynb ⭐
            └── readme.md 📖
```

# ⬇️Download Instructions⬇️
Download or clone this repository to get the files. Then using either Jupyter notebook or through the Jupyter addon on Visual Studio Code, open the file and run the cells of concern.
