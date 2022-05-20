# Solution 9 - serialintent

*EURECOM - Yavuz AKIN - 1 December 2021*

## Description of the problem

The server activity can be launched through an intent. This server sends as a response an intent containing an extra : an instance of the FlagContainer class. The problem is that the method required to read the flag is private and the flag attribute is private too. So a way to wrong the server needs to be found to have have access to required methods.

## Solution

The SerialActivity is launched through an intent taking into argument the name of SerialActivity's package and classname. The intent is sent to the SerialActivity activity by using startActivityForResult (inside the OnCreate method of the main activity) function to receive a response from it.

SerialActivity sends back a FlagContainer class instance inside the extras of the response intent. 

The response intent is processed inside the onActivityResult function. 

A FlagContainer class is also defined in our side to process the FlagContainer sent by SerialActivity.

This new FlagContainer class has the same package name and serialVersionUID number as the FlagContainer class from SerialActivity but with one difference:  
The getFlag() function is public. 

Since the system only looks at the class name, package name, and serialVersionUID number to determine that both FlagContainer classes are the same, no error is given and we can intercept the FlagContainer sent by SerialActivity and call the getFlag function on it to get the Flag.

## Optional Feedback

No optional feedback.
