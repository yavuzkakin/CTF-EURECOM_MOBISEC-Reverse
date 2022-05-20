# Solution 3 - gnirts

*EURECOM - Yavuz AKIN - 3 January 2022*

## Description of the problem

This challenge is similar in principal to the babyrev but more complicated because the conditions for the input to be accepted are more difficult to understand. 


## Solution
 
We use Ghidra again to decompile the code. We have FlagChecker class again.

Since the conditions are more difficult in this case, we can try to use dynamic analysis. Indeed a lot of functions are being used in this challenge for which we only need to have a result. 

First of all there are conditions similar to babyrev : 
 
- starts with "MOBISEC{"
- length of a given substring
- ...

Then the functions bim, bam, bum by using regex marking give conditions on the different type of inputs (lowercase, uppercase, numbers, ...) divisions within the input can have.

For dh,foo,gs,me,r we can use dynamic analysis to have the results they output without understanding what they do (although they're not that complicated, we just don't need to understand, for instance r is a basic reverse of string).

We execute these functions according to the decompiled code from Ghidra and we can access the other conditions on the flag. 



## Optional Feedback


