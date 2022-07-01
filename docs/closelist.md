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
