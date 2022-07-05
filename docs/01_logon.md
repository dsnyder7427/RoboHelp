---
layout: default
title: Markdown kitchen sink
nav_order: 2
---

# LOGON

The LOGON command logs you into Worldox Web. It is a POST request.

[LOGON Endpoint](#logon-endpoint)

[Request Body](#request-body)

[JSON Successful LOGON Response](#json-successful-logon-response)

[JSON Failed LOGON Response](#json-failed-logon-response)

## LOGON Endpoint
---------------

```
POST /cgi-bin/wdwebcgi.exe?LOGON/cgi-bin/wdwebcgi.exe?LOGON
```


## Request Body
------------

`HTMLOnOK`

This is the page to return on a successful call to LOGON.

```
v4\authentication\login.json
```

**Note:** api is deprecated but still can be used. Going forward v4 is the best practice.

`HTMLOnFail`

This is the page to return on a failed LOGON.

`V4\authentication\login.json`

**Note:** api is deprecated but still can be used. Going forward v4 is the best practice.

`wd_User_Code_Value`

Worldox Web Server User Code

`wd_User_Password_Value`

Worldox Web User Password



## JSON Successful LOGON Response

Note that when the response is successful, the `ErrorCount` value is blank.

```
"root": {
        "data": {
            "session": "mK2JN75CKK2NN643lsNiLAyWKr%242Ff2XB%242BvFn3ljbYex%242FEahK7OTXML5Daei0%243D",
            "servername": "_5D839152_51615_F",
            "user": "QC User1",
            "name": "QC1",
            "email": "qc1@worldox.com",
            "uploadFolder": "/cgi-bin/WDSIDS/mK2JN75CKK2NN643lsNiLAyWKr$2Ff2XB$2BvFn3ljbYex$2FEahK7OTXML5Daei0$3D/SAVE/upload-file.asp",
            "uploadFolderJSON": "/cgi-bin/WDSIDS/mK2JN75CKK2NN643lsNiLAyWKr$2Ff2XB$2BvFn3ljbYex$2FEahK7OTXML5Daei0$3D/SAVE/upload-file-json.asp",
            "ownerInital": "",
            "ErrorCount": "",
            "wd_Error_MSG": "",
            "Firm": "World Software Corporation",
            "OnlineHelp": "https://www.worldox.com/WEB3HELP/!SSL!/WebHelp/Introduction.htm",
            "WWTroubleShoot": "https://www.worldox.com/WEB3DOCS/Worldox%20Web%203.0%20Basics%20and%20Troubleshooting.pdf",
            "IISVER": "20201120",
            "AuthMethod": "b",
            "Graph": "3e58cb3b-1d02-4f55-b6a8-c113d1c2102c",
            "rsClient": "a0a571e5b8f0447c0c6c1cc9d00d7dee46ef6f1d97990c513aabcc04d260c7a9",
            "rsRedirect": "https://phoenix.wdsaas.com",
            "rsSecret": "ce0ea030382921255f858ccc2dbd748c308cfcd58878ce3e4d40c9ec3e4ad138"
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

## JSON Failed LOGON Response

Note that when the response has failed, the `ErrorCount` value has a number, the `RCTX` value determines what the error is. The Worldox API always returns a `200` status even on failure.  
```
{
    "root": {
        "data": {
            "session": "",
            "servername": "*",
            "user": "",
            "name": "qc1@worldox.com",
            "email": "",
            "uploadFolder": "/upload-file.asp",
            "uploadFolderJSON": "/upload-file-json.asp",
            "ownerInital": "",
            "ErrorCount": "1",
            "wd_Error_MSG": "WDRC_LOGON_USER_PASSWORD_INVALID",
            "Firm": "World Software Corporation",
            "OnlineHelp": "https://www.worldox.com/WEB3HELP/!SSL!/WebHelp/Introduction.htm",
            "WWTroubleShoot": "https://www.worldox.com/WEB3DOCS/Worldox%20Web%203.0%20Basics%20and%20Troubleshooting.pdf",
            "IISVER": "20201120",
            "AuthMethod": "b",
            "Graph": "3e58cb3b-1d02-4f55-b6a8-c113d1c2102c",
            "rsClient": "a0a571e5b8f0447c0c6c1cc9d00d7dee46ef6f1d97990c513aabcc04d260c7a9",
            "rsRedirect": "https://phoenix.wdsaas.com",
            "rsSecret": "ce0ea030382921255f858ccc2dbd748c308cfcd58878ce3e4d40c9ec3e4ad138"
        },
        "errorStatus": {
            "ErrorCount": "1",
            "wd_Error_RCID": "8435",
            "wd_Error_RCTX": "WDRC_LOGON_USER_PASSWORD_INVALID",
            "wd_Error_MSG": "WDRC_LOGON_USER_PASSWORD_INVALID",
            "wd_Error_VAR": "wd_USER_NAME_VALUE",
            "wd_Error_VAL": "The user name or password is incorrect. (WINRC#1326)",
            "wd_Error_DOCID": "",
            "wd_Error_DOCNAME": "",
            "req_ID": "",
            "Error": [
                {
                    "wd_Error_RCID": "8435",
                    "wd_Error_RCTX": "WDRC_LOGON_USER_PASSWORD_INVALID",
                    "wd_Error_MSG": "WDRC_LOGON_USER_PASSWORD_INVALID",
                    "wd_Error_VAR": "wd_USER_NAME_VALUE",
                    "wd_Error_VAL": "The user name or password is incorrect. (WINRC#1326)"
                }
            ]
        }
    }
}
 
```
