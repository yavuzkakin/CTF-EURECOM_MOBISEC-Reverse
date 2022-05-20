# Solution 4 - justask

*EURECOM - Yavuz AKIN - 26 November 2021*

## Description of the problem

By analyzing the Android Manifest of the application from the server. There are 4 activities that can return a response to our requests. These response intents contain the information required to compose the flag. So it is necessary to retrieve these intents and analyze them.

## Solution

For each of these activities, an intent is created. Inside the intent the class name (and action name if necessary) of the activities are given and the startActivityForResult function is used to launch the activities and receive their replies (with a request code so we can manage their replies)

Here is an example : 

```
Intent fmIntent1 =new Intent ();
        fmIntent1.setClassName("com.mobisec.justask","com.mobisec.justask.PartOne");
        startActivityForResult(fmIntent1,1);  
```

Inside the onActivityResult function:  

* The reponse intent of PartOne and PartTwo are converted to URI then String to receive the flag parts. 

* For PartThree, the flag is located inside a Bundle in the Extras of the response Intent.
* For PartFour, to get the flag it is required to parse through a series of Bundle containing Bundles. 


## Optional Feedback

No optional feedback.
