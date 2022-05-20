# Solution 3 - reachingout

*EURECOM - Yavuz AKIN - 26 November 2021*

## Description of the problem

In this challenge we have to connect to a server to print our its request and then send it back a reply using the POST method.

## Solution

First of all, permission to access the internet is given to the application through the manifest. 

In the onCreate function, we create a separate thread we first connect to 10.0.2.2:31337 which in turn asks us to connect to 10.0.2.2:31337/flag.

To this new URL, we create a HTTPURLConnection as a client and we get the input **buffered** stream (BufferedReader class is used).

Then, we connect again to the same URL, to send the response to the request we read previously which is 9.
To do this we use the POST method and a BufferedWriter:

```
HttpURLConnection client = (HttpURLConnection) url.openConnection();
                    client.setRequestMethod("POST");
                    client.setDoOutput(true);

                    OutputStream outputPost = new BufferedOutputStream(client.getOutputStream());
                    OutputStreamWriter outputStreamWriter = new OutputStreamWriter(outputPost);
                    BufferedWriter bufferedWriter = new BufferedWriter(outputStreamWriter);
                    bufferedWriter.write("answer=9");
```

This first response isn't enough. We read again the incoming stream and accordingly we send back the following response: 

```
bufferedWriter.write("answer=9&val1=3&oper=%2B&val2=6");
                    Log.i("MOBISEC","Output stream written");
                    bufferedWriter.flush();
```

And finally we read back the reply of the server which corresponds to the flag.

## Optional Feedback

No optional feedback.