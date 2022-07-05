# Upload to IIS

The UPLOAD to IIS command uploads the file to IIS. This is a POST request. It passes the file as form data in the Body.
**Note:** All POST requests that require a session require the session to be decoded either on the Body or as Parameter on the URL.
 
 ![Upload_IIS](assets/image/uploadiis.jpg)
 
**Note:** After you use UPLOAD to IIS, you can use the NEWFILE command.

17.1	UPLOAD to IIS Example
domain/CGI-BIN/WDSIDS/{session}/SAVE/upload-file.asp
17.2	JSON Successful Upload to IIS Response
Note that when the response is successful, the ErrorCount value is blank. 
{"message": "Your file uploaded successfully", "name":"archive-blah2.txt"}
17.3	JSON Failed Upload to IIS Response 
Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  
{"message": "Your file failed to upload"}
