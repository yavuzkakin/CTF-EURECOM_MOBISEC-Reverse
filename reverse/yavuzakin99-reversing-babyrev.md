# Solution 1 - babyrev

*EURECOM - Yavuz AKIN - 3 January 2022*

## Description of the problem

The target app babyrev takes as input a string and checks if it corresponds to the flag of the challenge through conditions given inside the FlagChecker. The problem is to find the flag in question.

## Solution

To solve this problem we use reverse engineering. We use the Ghidra decompiler to obtain the Java code of the babyrev.apk. 

Inside the code a FlagChecker class is defined for checking if our input is correct. The checkFlag function inside this class contains the conditions for which a flag is correct or not. 

The conditions in this case are pretty simple so we can perform static analysis.

Some of the conditions are :

- Starts with "MOBISEC{".
- Contains "this\_is_" after the 8th rank.
- We need to access the ressources, go inside the values, find a given address inside public.xml to see to which string it corresponds and take the string from the strings.xml to compare it with our input.
- The execution of a given part of the flag by a function needs to correspond to a given string. For instance the bam function seems to be the Ceasar encryption scheme
- In some functions (getR) a regex architecture is given to handle which elements are or not in lowercase letters.
- and other similar conditions.




## Optional Feedback

No optional feedback.
