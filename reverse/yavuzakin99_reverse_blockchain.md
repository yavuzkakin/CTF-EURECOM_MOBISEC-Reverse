# Solution 5 - blockchain

*EURECOM - Yavuz AKIN - 23 January 2022*

## Description of the problem

The blockchain apk takes as input a key and a flag. Inside the code, the key is being hashed with MD5. Three bytes are taken from this hashed key and they're hashed again. Then in a for tuple with size 10. The flag is being encrypted using AES-ECB at each iteration. The key for the encryption is the previously hashed value (issued from the the initial key). At each iteration this key is hashed again and used for encryption.

Finally the final encrypted value is compared to a string.


## Solution
 
Proceeding to a simple brute-force here would take too much time. Instead we know that only 3 bytes of the key matter. So we try all possible combinations of 3 bytes (128 possibilities per byte) and we hash them 10 times. We reproduce the inverse of the encryption algorithm (decryption) using the given string as the encrypted message, and the hashed combination of bytes as a key. 

This way the brute force is easier. When all combinations have been tried and the results saved. We can use a simple Ctrl+F to look for the flag.

## Optional Feedback


