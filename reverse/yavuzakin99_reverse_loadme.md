# Solution 6 - loadme

*EURECOM - Yavuz AKIN - 23 January 2022*

## Description of the problem

After reversing this apk, we can see that the Main Activity calls a class named DoStuff to verify the flag. This class contains a lot of functions, but we're gonna see basically that it is a dynamic code loader, that generates code to verify the flag. 


## Solution

First of all we focus on the DoStuff class. 

This class contains a lot of methods, lc, dc, gf, ...

For most of them we don't really need to understand the underlying mechanisms, we can use dynamic analysis to see the results they give. 

Most of the strings that are interesting are encrypted using the ds function (AES), we can decrypt them.

Basically, the da method gives us a part of the key. 

the dc method creates a HTTP connection with a url and downloads bytes from it into a file. 

Then the lc method reads this file and builds a class using the bytes it contains. 

Normally accessing this file can be difficult because permission is required in a android phone to have access to it. But we can use the Device File Explorer tool of Android Studio to have access to it and the new class. 

This new class is named LoadImage and it also performs dynamic code loading, so we need to go deeper ...

In this class we have similar methods to the precedent one. 

One part of the flag is given to us.

This time we load a file named logo.png from the reversed files (we took it from those reversed files and put it in the SD card of the emulated phone).

Finally by using the same method as before we load the class we extract it and when looking at the new class we can have all elements of the flag !

## Optional Feedback


