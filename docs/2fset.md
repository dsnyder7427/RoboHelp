---
layout: default
title: 2FSET
nav_order: 24
---

# 2FSET: ADD/EDIT/DELETE: TWO FACTOR AUTHENTICATION (2FA)

**Note:** You will need Worldox Web 3.0 Rev: 140311 or newer to use this API command.

You can use the ADD, EDIT and DELETE SET commands to add, edit or delete devices, email addresses and or cell phone numbers associated to accounts that use two factor authentication (2FA). These are POST requests.

**Note:** All POST requests that require a session require the session to be decoded either on the Body or as Parameter on the URL.

[2FSET Examples](#2fset-examples)

[2FSET Parameters](#2fset-parameters)

[JSON Successful Add a Record 2FSET Response](#json-successful-add-a-record-2fset-response)

[JSON Failed 2FSET Response](#json-failed-2fset-response)

## 2FSET Examples

### Add a Record

To add a record:

1: Make a POST request to 

`http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION}+HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json`

Pass the following into the body:

`wd_2FA_SendToAddr:` {Your email or cell phone # (number) of choice}

`wd_2FA_SENDOBJECT:` {What this action is for, e.g., Worldox}

`wd_2FA_SENDACTION:` {Why this action is, e.g., Worldox Web Authentication}

Once submitted and successful, the Response should return a Ref ID. An email or text will be sent with an access code. Both are needed for the next step.

2: Make another POST request to the same API (shown below) but change the Body. 
`http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION}+HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json` 

`wd_2FA_WORLDOXREF`: {REF ID from previous response}

`wd_2FA_ACCESSCODE`: {Access code from email or text}

3: Make a third POST request to the same API but change the Body once again.

`http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION}+HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json`

`wd_2FA_RecAddress`: {The email or cell phone # that will be stored}

`wd_2FA_RecContact`: {the email or cell phone #’s description}

`wd_2FA_RecEnabled`: {1 if the record should be enabled and 0 if the record is disabled}

Once successful, a new item should be added to the list.

### JSON Successful Add a Record JSON Response
Note that when the response is successful, the ErrorCount value is blank. 
{
    "root": {
        "errorStatus": {
            "List_ID": "",
            "List_Count": "",
            "ErrorCount": "",
            "Error": ""
        },
        "data": {
            "Ref": "Worldox 5FFC-B161",
            "AC": "1",
            "Send": "*****er@*****ox.***",
            "RMT": "69.112.37.92"
        }
    }
}

### JSON Failed Add a Record JSON Response

Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  

```
{
    "root": {
        "errorStatus": {
            "List_ID": "",
            "List_Count": "",
            "ErrorCount": "1",
            "Error": [
                {
                    "wd_Error_RCID": "8030",
                    "wd_Error_RCTX": "WDRC_2FA_ADDRESS_UNDEFINED",
                    "wd_Error_MSG": "Undefined Address\n\n\nThe email address entered for two factor authentication is not defined.\n\n\n\n\nOK\n",
                    "wd_Error_VAR": "",
                    "wd_Error_VAL": ""
                }
            ]
        },
        "data": {
            "Ref": "",
            "AC": "",
            "Send": "",
            "RMT": "69.112.37.92"
        }
    }
}
```

### Delete a Record

Make a POST request to the following API: 

`http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION} +HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json`

Pass the following into the body:

`wd_List_RecNum`: {The Rec Number you retrieved from 2FGET}

`wd_List_ID`: {The List Number you retrieved from 2FGET}

`wd_2FA_RecContract`: {Description of email or cell phone #}

`wd_2FA_RecEnabled`: {DELETE}

`wd_2FA_RecAddress`: {Cell phone # or email}

### JSON Successful Delete a Record JSON Response

Note that when the response is successful, the ErrorCount value is blank. 

```
{
    "root": {
        "errorStatus": {
            "List_ID": "x256FAC8",
            "List_Count": "",
            "ErrorCount": "",
            "Error": ""
        },
        "data": {
            "Ref": "",
            "AC": "",
            "Send": "",
            "RMT": "69.112.37.92"
        }
    }
}
]
```

###	JSON Failed Delete a Record JSON Response

Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  

```
{
    "root": {
        "errorStatus": {
            "List_ID": "x256B2F8",
            "List_Count": "",
            "ErrorCount": "1",
            "Error": [
                {
                    "wd_Error_RCID": "8740",
                    "wd_Error_RCTX": "WDRC_SID_INVALID",
                    "wd_Error_MSG": "WDRC_SID_INVALID",
                    "wd_Error_VAR": "wd_SID",
                    "wd_Error_VAL": "null"
                }
            ]
        },
        "data": {
            "Ref": "",
            "AC": "",
            "Send": "",
            "RMT": "69.112.37.92"
        }
    }
}
```

### Edit a Record

To edit an existing record, there are a couple of steps.

1: Make a POST request to the following API:

`http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION}+HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json`

Depending upon the Description and/or whether the enabled/disabled item has changed, this is the only step you need to update the record. Pass the following into the Body.

`wd_List_RecNum`: {The Rec Number you retrieved from 2FGET}

`wd_List_ID`: {The List Number you retrieved from 2FGET}

`wd_2FA_RecContract`: {Description of email or cell phone #}

`wd_2FA_RecEnabled`: {1 whether the record should be enabled and 0 if the record is disabled}

`wd_2FA_RecAddress`: {Cell phone # or email}

If the enabled cell phone #/email and/or Description has changed, you will need to do the following steps. Pass the following into the Body:

`wd_2FA_SendToAddr`: {Your email or cell phone # of choice}

`wd_2FA_SENDOBJECT`: {What this action is for e.g Worldox}

`wd_2FA_SENDACTION`: {Why this action is e.g Worldox Web Authentication}

Once submitted and successful, the Response should return a Ref ID. An email or text will be sent with an access code. Both are needed for the next step.

2: Make another POST request to the same API but change the Body.

`http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION} +HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json`

`wd_2FA_WORLDOXREF`: {REF ID from previous response},

`wd_2FA_ACCESSCODE`: {Access code from email or text}

3: Make a third POST request to the same API but change the Body once again.

`http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION} +HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json`

`wd_List_RecNum`: {The Rec Number you retrieved from 2FGET}

`wd_List_ID`: {The List Number you retrieved from 2FGET}

`wd_2FA_RecContract`: {Description of email or cell phone #}

`wd_2FA_RecEnabled`: {1 if the record should be enabled and 0 if the record is disabled}

`wd_2FA_RecAddress`: {Cell phone # or email}
 
### JSON Successful Edit a Record JSON Response

Note that when the response is successful, the ErrorCount value is blank. 

```
{
    "root": {
        "errorStatus": {
            "List_ID": "",
            "List_Count": "",
            "ErrorCount": "",
            "Error": ""
        },
        "data": {
            "Ref": "Worldox 5FFF-5042",
            "AC": "1",
            "Send": "*****er@*****ox.***",
            "RMT": "69.112.37.92"
        }
    }
}
```

### JSON Failed Edit a Record JSON Response

Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  

```
{
    "root": {
        "errorStatus": {
            "List_ID": "x214E1A8",
            "List_Count": "",
            "ErrorCount": "1",
            "Error": [
                {
                    "wd_Error_RCID": "8375",
                    "wd_Error_RCTX": "WDRC_LISTID_INVALID",
                    "wd_Error_MSG": "Invalid list ID issue\n\n\nInvalid list ID, click Refresh to update your file list.\n\n\n\ncloseCircle, wdErrorIco\nRefresh\nCancel",
                    "wd_Error_VAR": "",
                    "wd_Error_VAL": ""
                }
            ]
        },
        "data": {
            "Ref": "",
            "AC": "",
            "Send": "",
            "RMT": "69.112.37.92"
        }
    }
}
```


