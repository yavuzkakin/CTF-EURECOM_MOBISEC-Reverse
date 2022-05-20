# Solution 4 - goingnative

*EURECOM - Yavuz AKIN - 24 January 2022*

## Description of the problem

This apk contains native and java code. In order to find the flag we have to reverse both these type of codes.



## Solution
 
We reverse the java code using jadx and the native code using Ghidra (Ghidra gives us many native code but they all do the same, they are just adapted to differents processors).

In the Java code, there is a FlagChecker class that verifies the flag starts with "MOBISEC{" and end with "}" then proceeds to another check by calling the function helloFromTheOtherSide.

The helloFromTheOtherSide function is implemented in native code. We use Ghidra to reverse it.

in Ghidra, the code verifies the flag. 
__s is the adress of the flag string. It starts with 'n'. The following characters are compared to 'ative' so the flag starts with 'native'.

Then in the if statement, we learn the positions of the '_' and that there is a 'is' after "native\_".

The last comparison gives us the 'so' and finally the flag finishes with a set of 6 digits.


## Optional Feedback


