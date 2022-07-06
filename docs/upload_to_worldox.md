---
layout: default
title: NEWFILE
nav_order: 16
---
# UPLOAD TO WORLDOX

The UPLOAD command takes the uploaded file of an existing document and overwrites it or creates a new version of the file that exists in Worldox. This is a GET request. Note: Upload to IIS and NEWFILE must be performed before Upload to Worldox.

[UPLOAD to_Worldox Example](#upload-to-worldox-example)

[UPLOAD to Worldox Parameters](#upload-to-worldox-parameters)

[JSON Successful UPLOAD to Worldox Response](#json-successful-upload-to-worldox-response)

[JSON Failed UPLOAD to Worldox Response](#json-failed-upload-to-worldox-response)

## UPLOAD to Worldox Example

`{{url}}/cgi-bin/wdwebcgi.exe?UPLOAD&wd_SID={{session}}&HtmlOnOK=/v4/fileActions/uploadVerb.json&HtmlOnFail=/v4/fileActions/uploadVerb.json&Wd_File_StatusFlags_Value={{wdStatusFlag}}&wd_FILE_FILENAME_VALUE={{wdFileName}}&Wd_List_RecNum={{newFileRC}}&wd_List_ID={{newFileID}}`

## UPLOAD to Worldox Parameters

`HTMLOnOK`

	This is the page to return on a successful call to UPLOAD.
	`v4\fileActions\uploadPassed.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`HTMLOnFail`

	This is the page to return on a failed UPLOAD.
	
	`v4\fileActions\uploadFailed.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`{Worldox Web Domain}`
	
	Is the domain name

`wd_SID`

	This command is the Worldox session ID.

`wd_FILE_STATUSFLAGS_VALUE`

	Security ID flag (indicates if the file has security and if so, what type- none, protected or hidden)

`wd_File_FileName_Value`

	Is the name of the file that was uploaded to IIS
`wd_List_RecNum`

	Use the same FileRN (recnum) that is returned from NEWFILE.

`wd_List_ID`

	Use the same FileLID (file list ID) that is returned from NEWFILE.
## JSON Successful Upload to Worldox Response

Note that when the response is successful, the ErrorCount value is blank. 

```
{
    "root": {
        "data": {
            "Name": "Qc4 test upload from postman again (00016628x51615).DOCX"
        },
        "errorStatus": {
            "ErrorCount": "",
            "wd_Error_RCID": "",
            "wd_Error_RCTX": "",
            "wd_Error_MSG": "",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "wd_Error_DOCID": "",
            "wd_Error_DOCNAME": "",
            "req_ID": "",
            "Error": ""
        }
    }
}
```
 
## JSON Failed Upload to Worldox Response

Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure. 

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">

<head>
    <meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1" />
    <title>502 - Web server received an invalid response while acting as a gateway or proxy server.</title>
    <style type="text/css">
        <!--
        body {
            margin: 0;
            font-size: .7em;
            font-family: Verdana, Arial, Helvetica, sans-serif;
            background: #EEEEEE;
        }

        fieldset {
            padding: 0 15px 10px 15px;
        }

        h1 {
            font-size: 2.4em;
            margin: 0;
            color: #FFF;
        }

        h2 {
            font-size: 1.7em;
            margin: 0;
            color: #CC0000;
        }

        h3 {
            font-size: 1.2em;
            margin: 10px 0 0 0;
            color: #000000;
        }

        #header {
            width: 96%;
            margin: 0 0 0 0;
            padding: 6px 2% 6px 2%;
            font-family: "trebuchet MS", Verdana, sans-serif;
            color: #FFF;
            background-color: #555555;
        }

        #content {
            margin: 0 0 0 2%;
            position: relative;
        }

        .content-container {
            background: #FFF;
            width: 96%;
            margin-top: 8px;
            padding: 10px;
            position: relative;
        }
        -->
    </style>
</head>

<body>
    <div id="header">
        <h1>Server Error</h1>
    </div>
    <div id="content">
        <div class="content-container">
            <fieldset>
                <h2>502 - Web server received an invalid response while acting as a gateway or proxy server.</h2>
                <h3>There is a problem with the page you are looking for, and it cannot be displayed. When the Web
                    server (while acting as a gateway or proxy) contacted the upstream content server, it received an
                    invalid response from the content server.</h3>
            </fieldset>
        </div>
    </div>
</body>

</html>
```
