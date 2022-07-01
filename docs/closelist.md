# CLOSELIST

The CLOSELIST command closes the Worldox Web file list.

[CLOSELIST Example](#closelist-example)

[CLOSELIST Parameters](#closelist-parameters)

[JSON Successful CLOSELIST Response](#json-successful-closelist-response)

[JSON Failed CLOSELIST Response](#json-failed-closelist-response)

## CLOSELIST Example
`/cgi-bin/wdwebcgi.exe?CLOSELIST&wd_SID={{session}}`

## CLOSELIST Parameters
`wd_SID`
The Worldox session ID
`wd_List_ID`
The Worldox list to close
`HTMLOnOK`
This is the page to return on a successful call to CLOSELIST.
`v4\fileActions\closeList.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`HTMLOnFail`
This is the page to return on a failed CLOSELIST.
`v4\fileActions\closeList.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

## JSON Successful CLOSELIST Response

Note that when the response is successful, the `ErrorCount` value is blank. 
```{
    "root": {
        "errorStatus": {
            "ErrorCount": "",
            "wd_Error_RCID": "",
            "wd_Error_RCTX": "",
            "wd_Error_MSG": "",
            "wd_Error_VAR": "",
            "wd_Error_VAL": ""
        },
        "data": ""
    }
}```

## JSON Failed CLOSELIST Response

Note that when the response has failed, the `ErrorCount` value has a number, the `RCTX` value determines what the error is. The Worldox API always returns a `200` status even on failure.  

```{
    "root": {
        "errorStatus": {
            "ErrorCount": "1",
            "wd_Error_RCID": "8380",
            "wd_Error_RCTX": "WDRC_LISTID_UNDEFINED",
            "wd_Error_MSG": "Error no List ID\nYour request returned without a 'List ID', please refresh.\n\n\n\n\nlock, wdInfo\ncloseCircle, wdErrorIco\n\nRefresh\n",
            "wd_Error_VAR": "",
            "wd_Error_VAL": ""
        },
        "data": ""
    }
}```
