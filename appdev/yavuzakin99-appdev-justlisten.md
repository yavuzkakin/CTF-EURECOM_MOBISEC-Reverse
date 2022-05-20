# Solution 2 - justlisten

*EURECOM - Yavuz AKIN - 26 November 2021*

## Description of the problem

In this challenge the flag is broadcasted on the system using an implicit intent. In order to retrieve the flag the intent must be retrieved and analyzed. 

## Solution

In order to retrieve the intent a Broadcast Receiver is used. 

The Broadcast Receiver can be Manifest-declared or Context-registered. Both methods have been tried in this challenge:  

* Manifest-declared Receivers are declared in the manifest with the corresponding intent filter and intent action:  

```
<receiver android:name=".MyBroadcastReceiver"  android:exported="true">
            <intent-filter>
                <action android:name="com.mobisec.intent.action.FLAG_ANNOUNCEMENT" />
            </intent-filter>
        </receiver>    
``` 
* Context-registered Receivers are declared in the onCreate function of the Main Activity.

```
BroadcastReceiver br = new MyBroadcastReceiver();

IntentFilter filter = new IntentFilter(ConnectivityManager.CONNECTIVITY_ACTION);
filter.addAction("com.mobisec.intent.action.FLAG_ANNOUNCEMENT");
this.registerReceiver(br, filter);
```        
A BroadcastReceiver class is implemented. Inside the OnReceive function of the class, the intent is converted to URI, then to String and is printed as a log to view the flag.


## Optional Feedback

No optional feedback.
