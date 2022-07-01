# DOWNLOAD

The DOWNLOAD command prepares a file for download. This is a GET request.

[DOWNLOAD Example](#download-example)

[DOWNLOAD Parameters](#download-parameters)

[JSON Successful DOWNLOAD Response](#json-successful-download-response)

[JSON Failed DOWNLOAD Response](#json-failed-download-response)

## DOWNLOAD Example
`{Worldox Web Domain}  +  'cgi-bin/wdwebcgi.exe?DOWNLOAD&wd_SID=' + {Worldox Web User Session) + '&html=v4/fileActions/download.json&wd_List_RecNum=' + x.RN + '&wd_List_ID=' + x.LID + '&wd_List_Offset=' + x.LN`

## DOWNLOAD Parameters
`HTMLOnOK`
This is the page to return on a successful call to DOWNLOAD.
v4 \fileActions\download.json

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.
`HTMLOnFail`
This is the page to return on a failed DOWNLOAD.
`v4 \fileActions\download.json`
**Note:** `api`  is deprecated but still can be used. Going forward v4 is the best practice.
`{Worldox Web Domain}` 
	Is the domain name.
`wd_SID`
	Is the session ID
`{Worldox Web User Session)`
	Is the variable
`wd_List_RecNum`
Is the record number of the files in the list that you want to download.
`wd_List_ID`
Is the record number of the file on the list that you want to download 
`wd_List_Offset`
(Starting offset) set to 1


## JSON SUCCESSFUL DOWNLOAD Response

Note that when the response is successful, the `ErrorCount` value is blank. 
**Note:** You can view the file’s location in the fileLoc line. You can view the file’s name in the `FileNme` line. 

```
{
    "root": {
        "data": {
            "fileLoc": "/cgi-bin/WDSIDS/1FZMVYfcOQrBNmi8kr3HWUuwCGHwTYqLNJX4XMEokPlk0D2sQKhwMWBz2FE%243D/OPEN/005/20000/200/Terms%20and%20Conditions%20of%20QC%20%2800001079-2x51615%29.DOC",
            "FileNme": "Terms%20and%20Conditions%20of%20QC%20%2800001079-2x51615%29.DOC",
            "FileZMS": "\\WORLDOX\\ZMS\\005\\20000\\200\\00001079.DOC"
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

## JSON FAILED DOWNLOAD Response

Note that when the response has failed, the `ErrorCount` value has a number, the `RCTX` value determines what the error is. The Worldox API always returns a `200` status even on failure.  

```
{
    "root": {
        "data": {
            "fileLoc": "",
            "FileNme": "",
            "FileZMS": ""
        },
        "errorStatus": {
            "ErrorCount": "2",
            "wd_Error_RCID": "8525",
            "wd_Error_RCTX": "WDRC_PATH_INVALID",
            "wd_Error_MSG": "Invalid Path\n\n\nThe path is invalid.\n\n\n\n\nOK\n",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "wd_Error_DOCID": "",
            "wd_Error_DOCNAME": "",
            "req_ID": "",
            "Error": [
                {
                    "wd_Error_RCID": "8525",
                    "wd_Error_RCTX": "WDRC_PATH_INVALID",
                    "wd_Error_MSG": "Invalid Path\n\n\nThe path is invalid.\n\n\n\n\nOK\n",
                    "wd_Error_VAR": "",
                    "wd_Error_VAL": ""
                },
                {
                    "wd_Error_RCID": "8380",
                    "wd_Error_RCTX": "WDRC_LISTID_UNDEFINED",
                    "wd_Error_MSG": "Error no List ID\nYour request returned without a 'List ID', please refresh.\n\n\n\n\nlock, wdInfo\ncloseCircle, wdErrorIco\n\nRefresh\n",
                    "wd_Error_VAR": "",
                    "wd_Error_VAL": ""
                }
            ]
        }
    }
}
```
