---
layout: default
title: UNLOCK
nav_order: 27
---

# UNLOCK

The UNLOCK command unlocks a locked record.

[UNLOCK Example](#unlock-example)

[JSON Successful UNLOCK Response](#json-successful-unlock-response)

[JSON Failed RENAME Response](#json-failed-rename-response)

## UNLOCK Example

The way to unlock a record is to call LOCK again but DO NOT pass a wd_list_RecNum. See [LOCK](https://dsnyder7427.github.io/Worldox-Web-API/lock.html) for details.

## JSON Successful UNLOCK Response

Note that when the response is successful, the ErrorCount value is blank. 

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

## JSON Failed UNLOCK Response

Note that when the response has failed, the `ErrorCount` value has a number, the `RCTX` value determines what the error is. The Worldox API always returns a `200` status even on failure. 

```
{
    "root": {
        "data": {
            "session": "jgHWxvx%242BNy6bcj4UcSzd135QNRzTNiGUu62hlo2GgX58fH6C26vn5yauzd8%243D",
            "List_ID": ""
        },
        "errorStatus": {
            "ErrorCount": "2",
            "wd_Error_RCID": "8380",
            "wd_Error_RCTX": "WDRC_LISTID_UNDEFINED",
            "wd_Error_MSG": "Error no List ID\nYour request returned without a 'List ID', please refresh.\n\n\n\n\nlock, wdInfo\ncloseCircle, wdErrorIco\n\nRefresh\n",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "wd_Error_DOCID": "",
            "wd_Error_DOCNAME": "",
            "req_ID": "",
            "Error": [
                {
                    "wd_Error_RCID": "8380",
                    "wd_Error_RCTX": "WDRC_LISTID_UNDEFINED",
                    "wd_Error_MSG": "Error no List ID\nYour request returned without a 'List ID', please refresh.\n\n\n\n\nlock, wdInfo\ncloseCircle, wdErrorIco\n\nRefresh\n",
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
