# Solution 6 - whereareyou

*EURECOM - Yavuz AKIN - 26 November 2021*

## Description of the problem

In this challenge, a Service that receives a request through the startService() function and that as a reply sends back the current location of the device needs to be implemented. It is important here to have the correct permissions.

## Solution

In order to access the current location, we provide the permissions to the application to accees our location in the manifest :  
` <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />`
    `<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />  
`
  
An Intent filter is put in the Main Activity for the action "com.mobisec.intent.action.GIMMELOCATION".

In the Main Activity, a function named getCurrentLocation is created in which a LocationManager and a LocationListener classes and instanced.

The LocationManager requests a location update through the requestLocationUpdates function.  

The LocationListener has an overidden function named onLocationChanged which when the location of the system has been updated, creates an intent with the action "com.mobisec.intent.action.LOCATION_ANNOUNCEMENT" and with the location as an extra and broadcasts it to the system. 


## Optional Feedback

No optional feedback.
