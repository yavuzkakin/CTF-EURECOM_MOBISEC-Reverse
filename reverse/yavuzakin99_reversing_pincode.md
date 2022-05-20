# Solution 2 - pincode

*EURECOM - Yavuz AKIN - 3 January 2022*

## Description of the problem

This time the verification is more complicated since the verification of the flag is not performed on the flag itself but on a 25*400 times hashed version of the flag. 

## Solution

For the input to be accepted the 25*500 times hashed version of the input needs to correspond to :

d04988522ddfed3133cc24fb6924eae9

The hashing method used is MD5. 

The flag is a PIN code, so it is only composed of numbers and it is of length 6. 

In this particular case we can try to breakforce the system by trying to hash 25*400 times all the possible combinations of digits from 0 to 9 of length 6 and stop when one of them corresponds to the final hash. 

To do this I have used Python and got a result in approximately 2 hours at the 703958th iteration. 



## Optional Feedback


