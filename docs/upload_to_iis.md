---
layout: default
title: UPLOAD to IIS
nav_order: 14
---

# Upload to IIS

The UPLOAD to IIS command uploads the file to IIS. This is a POST request. It passes the file as form data in the Body.

[UPLOAD to IIS Example](#upload-to-iis-example)

[JSON Successful UPLOAD to IIS Response](#json-successful-upload-to-iis-response)

[JSON Failed UPLOAD_to_IIS Response](#json-failed-upload-to-IIS-response)


**Note:** All POST requests that require a session require the session to be decoded either on the Body or as Parameter on the URL.
 
![upload iis](/docs/images/upload_iis.png)

 
**Note:** After you use UPLOAD to IIS, you can use the NEWFILE command.

## UPLOAD to IIS Example

`domain/CGI-BIN/WDSIDS/{session}/SAVE/upload-file.asp`

## JSON Successful Upload to IIS Response

Note that when the response is successful, the ErrorCount value is blank. 

`{"message": "Your file uploaded successfully", "name":"archive-blah2.txt"}`

## JSON Failed Upload to IIS Response 

Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  

`{"message": "Your file failed to upload"}`
