---
layout: default
title: 2FGET
nav_order: 23
---

## 2FGET: TWO FACTOR AUTHENTICATION (2FA)

**Note:** You will need Worldox Web 3.0 Rev: 140311 or newer to use this API command.

Gets the list. This is a GET request.

To elaborate, the 2FGET command retrieves a list of devices, email addresses and cell phone numbers used for two factor authentication (2FA). Two factor authentication can protect Worldox Web 3.x from unauthorized access by setting a program password or using a password combined with an access code.  Worldox Web 3.x will prompt an end user to enter it when you first launch it or if you unlocked your PC or device and need to regain access to Worldox Web 3.x. 

### 2FGET Example 

`http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FGET+wd_SID={SESSION} +HTMLOnOk=/v4/authentication/twoFactorDevice.json+HTMLOnFail=/v4/authentication/twoFactorDevice.json`

This will return the entire list.

## 2FGET Parameters

`wd_SID`

The Worldox session ID

`HTMLOnOK`

This is the page to be returned on a success.

`HTMLOnFAIL`

This is the page to be returned on a failure.

`WD_List_Filter`

`Redact>0`. If Redact is set to be less than 0, contact information is shown. 

`Redact>1`. If Redact is set to be less than 1, asterisks appear in the output to hide email addresses or phone numbers.

If

`WD_List_Filter=Redact>0`

Contact information (email addresses or cell phone numbers) are shown:

```
{
"Rec": "1",
"L": "2",
"ADDR": "(555) 279-5579",
"ADDR.ASIS": "+1555279579",
"ADDR.VIEW": "(555) 279-5579",
"NAME": "John’s Cell",
"FLAG": "Yes"
},
```

If

`WD_List_Filter=Redact>1`

Email addresses are hidden with asterisks:{

```
"Rec":"1",
"L":"2",
"ADDR":"(***) ***-**79",
"ADDR.ASIS":"+*********79",
"ADDR.VIEW":"(***) ***-**79",
"NAME":"John’s Cell",
"FLAG":"Yes"
},
```

## JSON Successful 2FGET Response

Note that when the response is successful, the ErrorCount value is blank. 

```
{
    "root": {
        "errorStatus": {
            "List_ID": "x211D3D8",
            "List_Count": "2",
            "ErrorCount": "",
            "wd_Error_RCID": "",
            "wd_Error_RCTX": "",
            "wd_Error_MSG": "",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "Error": ""
        },
        "data": [
            {
                "Rec": "1",
                "L": "1",
                "ADDR": "(551) 655-5721",
                "ADDR.ASIS": "+15516555721",
                "ADDR.VIEW": "(551) 655-5721",
                "FLAG": "Yes"
            },
            {
                "Rec": "2",
                "L": "2",
                "ADDR": "dsnyder@worldox.com",
                "ADDR.ASIS": "dsnyder@worldox.com",
                "ADDR.VIEW": "dsnyder@worldox.com",
                "FLAG": "Yes"
            }
        ]
    }
}
```

## JSON Failed 2FGET Response

Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  

```
{
    "root": {
        "errorStatus": {
            "List_ID": "",
            "List_Count": "",
            "ErrorCount": "1",
            "wd_Error_RCID": "8740",
            "wd_Error_RCTX": "WDRC_SID_INVALID",
            "wd_Error_MSG": "WDRC_SID_INVALID",
            "wd_Error_VAR": "wd_SID",
            "wd_Error_VAL": "pQG7rtsguFSwdhnaBLtpvrtxOwZoDI4bGO3EnXdTMRHy1bqg1FctD7A6Gw8$3Dkopkp[wy",
            "Error": [
                {
                    "wd_Error_RCID": "8740",
                    "wd_Error_RCTX": "WDRC_SID_INVALID",
                    "wd_Error_MSG": "WDRC_SID_INVALID",
                    "wd_Error_VAR": "wd_SID",
                    "wd_Error_VAL": "pQG7rtsguFSwdhnaBLtpvrtxOwZoDI4bGO3EnXdTMRHy1bqg1FctD7A6Gw8$3Dkopkp[wy"
                }
            ]
        },
        "data": [
            {
                "Rec": "%:R#%",
                "L": "%:L#%",
                "ADDR": "%:ADDR%",
                "ADDR.ASIS": "%:ADDR.ASIS%",
                "ADDR.VIEW": "%:ADDR.VIEW%",
                "NAME": "%:NAME%",
                "FLAG": "%:FLAG%"
            }
        ]
    }
}
```

