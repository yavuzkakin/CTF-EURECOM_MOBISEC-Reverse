# Solution 5 - filehasher

*EURECOM - Yavuz AKIN - 26 November 2021*

## Description of the problem

The problem here is that we need to calculate the hash of the file that the server sends us through an intent (a filepath to be precise). The server gives the flag if the hash corresponds to what it is expecting.

## Solution

Inside the manifest file, an Intent filter for Intents with action name `"com.mobisec.intent.action.HASHFILE"`is created.

In the Main Activity, in the onCreate function, the `getIntent()` function is used to get the Intent from the server. 

We use the following code to get the path given in the  Uri of the Intent: 
`String path= new String(uri.getPath());`

A calcHash function is created to calculate the Hash of the given file. This function uses the MessageDigest class with the instance "SHA256" to calculate the hash of the file :
  
```  
public String calcHash(String filepath) throws NoSuchAlgorithmException, FileNotFoundException, 
IOException {
        MessageDigest md = MessageDigest.getInstance("SHA256");
        File file = new File(filepath);
        String str= new String(Files.readAllBytes(file.toPath()));
        md.update(str.getBytes());
        byte[] digest = md.digest();
        return byteArrayToHex(digest);
    }  
```

A result Intent is created, with the hash as an extra. And is sent to the server using the setResult function with the RESULT_OK result code. 
## Optional Feedback

No optional feedback.
