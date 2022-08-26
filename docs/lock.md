---
layout: default
title: LOCK
nav_order: 13
---

# LOCK

The LOCK command locks a record for exclusive use.

[LOCK Example](#lock-example)

[LOCK Parameters](#lock-parameters)

[JSON Successful LOCK Response](#json-successful-lock-response)

[JSON Failed LOCK Response](#json-failed-lock-response)


## LOCK Example

`/cgi-bin/wdwebcgi.exe?LOCK+wd_SID={{session}}+wd_List_ID={{listid}}+wd_List_RecNum={{recnum}}`

## LOCK Parameters

`wd_SID`

  The Worldox session ID

Optional:
`wd_List_ID`

  The active list

`wd_List_RecNum`
  
  The record to lock

`HTML`

  
 `v4\fileActions\fileStatus.json` generic metadata output with errors.

## JSON Successful LOCK Response

Note that when the response is successful, the `ErrorCount` value is blank. 

```
{
    "root": {
        "data": {
            "session": "EHgRICvIKW4FNzZGxI%242Fxw6XR7Ag0Y5zbpsntEjhfiLLdCTZkz%242BaFbdWCx%242F4%243D",
            "List_ID": "x269CA70"
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

## JSON Failed LOCK Response

```
{
    "root": {
        "data": {
            "session": "TtKSsSbvV2hb9nEKP9qiLB2vUfQL8RTNPuuaS%242F6yaCDZlFEPk7QkXGm6cz8%243D",
            "List_ID": "x1B3BDC0"
        },
        "errorStatus": {
            "ErrorCount": "2",
            "wd_Error_RCID": "8375",
            "wd_Error_RCTX": "WDRC_LISTID_INVALID",
            "wd_Error_MSG": "Invalid list ID issue\n\n\nInvalid list ID, click Refresh to update your file list.\n\n\n\ncloseCircle, wdErrorIco\nRefresh\nCancel",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "wd_Error_DOCID": "",
            "wd_Error_DOCNAME": "",
            "req_ID": "",
            "Error": [
                {
                    "wd_Error_RCID": "8375",
                    "wd_Error_RCTX": "WDRC_LISTID_INVALID",
                    "wd_Error_MSG": "Invalid list ID issue\n\n\nInvalid list ID, click Refresh to update your file list.\n\n\n\ncloseCircle, wdErrorIco\nRefresh\nCancel",
                    "wd_Error_VAR": "",
                    "wd_Error_VAL": ""
                },
                {
                    "wd_Error_RCID": "1208",
                    "wd_Error_RCTX": "An extended error has occurred. (WINRC#1208)",
                    "wd_Error_MSG": "",
                    "wd_Error_VAR": "",
                    "wd_Error_VAL": ""
                }
            ]
        }
    }
}
```
