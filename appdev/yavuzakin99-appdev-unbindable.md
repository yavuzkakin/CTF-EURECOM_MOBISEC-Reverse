# Solution 8 - unbindable

*EURECOM - Yavuz AKIN - 1 December 2021*

## Description of the problem

The problem is to obtain the Flag from a Service by binding to it. The code of the Service needs to be understood in order to interact with it to finally receive the flag.

## Solution

First of all in the onCreate function, an intent is sent to bind with the UnbindableService (by using the bindService function).

We define a ServiceConnection class (class for interacting with the main interface of the server), and modify the onServiceConnected function. 
In this function we create a Messenger to send two messages to the Service : one to subscribe to it, and another to receive the flag.

Then by using a IncomingHandler class, we retrieve the reply of the service which contains the flag we are looking for.


## Optional Feedback

No optional feedback.
