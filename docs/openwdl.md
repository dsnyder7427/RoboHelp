---
layout: default
title: OPENWDL
nav_order: 17
---
# OPENWDL (CREATE TEMP WDL) 

The OPENWDL command creates a temporary WDL or project in Worldox. 

[OPENWDL Example](#openwdl-example)
[OPENWDL Parameters](#openwdl-parameters)
[JSON Successful OPENWDL Response](#json-successful-openwdl-response)
[JSON Failed OPENWDL Response](#json-failed-openwdl-response)

## OPENWDL Example

`{{url}}/cgi-bin/wdwebcgi.exe?OPENWDL&wd_SID={{session}}&HTMLOnOk=/v4/fileList/wdlList.json&HTMLOnFail=/v4/fileList/wdlList.json&Wd_File_Pathfile_Value=new`

## OPENWDL Parameters

`HTMLOnOK`

	This is the page to return on a successful call to OPENWDL.
	
	`/v4/fileList/wdlList.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`HTMLOnFail`

	his is the page to return on a failed OPENWDL.
	`/v4/fileList/wdlList.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`wd_File_Pathfile_Value`
	
	`new` specifies if it is a new WDL. 

`wd_SID`
	
	Is the session ID
	
## JSON Successful OPENWDL Example

Note that when the response is successful, the ErrorCount value is blank. 

```
{
    "root": {
        "data": {
            "path": "%25WDTEMPPATH%25%5C%24WD89F008955FFCBC950000007F.WDL"
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

## JSON Failed OPENWDL Example

Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  

```
{
    "root": {
        "data": {
            "path": ""
        },
        "errorStatus": {
            "ErrorCount": "1",
            "wd_Error_RCID": "8740",
            "wd_Error_RCTX": "WDRC_SID_INVALID",
            "wd_Error_MSG": "WDRC_SID_INVALID",
            "wd_Error_VAR": "wd_SID",
            "wd_Error_VAL": "11hi51BmPi7CL5gD9TRI8QmM$2F3SJgyID2lrcYOZu$2BIQSojPGB9f7Y0pxA6Y$3Dykytr",
            "wd_Error_DOCID": "",
            "wd_Error_DOCNAME": "",
            "req_ID": "",
            "Error": [
                {
                    "wd_Error_RCID": "8740",
                    "wd_Error_RCTX": "WDRC_SID_INVALID",
                    "wd_Error_MSG": "WDRC_SID_INVALID",
                    "wd_Error_VAR": "wd_SID",
                    "wd_Error_VAL": "11hi51BmPi7CL5gD9TRI8QmM$2F3SJgyID2lrcYOZu$2BIQSojPGB9f7Y0pxA6Y$3Dykytr"
                }
            ]
        }
    }
}
```
