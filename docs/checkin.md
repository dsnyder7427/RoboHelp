---
layout: default
title: CHECKIN
nav_order: 5
---

# CHECKIN

The CHECKIN command checks in a file at the given record number and list ID. It is a GET request.

[CHECKIN Example](#checkin-example)

[CHECKIN Parameters](#checkin-parameters)

[JSON Successful CHECKIN Response](#json-successful-checkin-response)

[JSON Failed CHECKIN Response](#json-failed-checkin-response)

## CHECKIN Example
`{Worldox Web Domain}  + 'cgi-bin/wdwebcgi.exe?CHECKIN+wd_SID='  + {Worldox Web User Session) + '&Wd_List_RecNum=' + x.RN + '&wd_List_ID=' + x.LID + '&HTMLOnOK=/v4/fileActions/fileStatus.json&HTMLOnFail=/v4/fileActions/fileStatus.json'`

## Checkin Parameters

`HTMLOnOK`

This is the page to return on a successful call to CHECKIN.

`v4\fileActions\checkinPassed.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`HTMLOnFail`

This is the page to return on a failed CHECKIN.

`v4\fileActions\checkinFailed.json`

**Note:** `api`is deprecated but still can be used. Going forward v4 is the best practice.

`{Worldox Web Domain}`
	Is the domain name
`wd_SID`
	Is the session ID
`{Worldox Web User Session)`
	Is the variable
`wd_List_RecNum`
Is the record number of the files in the list that you want to check in.
`wd_List_ID`
Is the list ID. Parameter previously returned from FINDFILES. 
 
## JSON Successful CHECKIN Response

Note that when the response is successful, the `ErrorCount` value is blank. 

```
{
    "root": {
        "data": {
            "XN": "Terms and Conditions of QC",
            "LN": "x26BD9D8",
            "RN": "1",
            "FN": "1",
            "C": "",
            "PF": "Client Files\\20000\\200\\00001079.DOC",
            "V": "2",
            "O": "QC User4 (QC4)",
            "1C": "20000",
            "1D": "City of Mesa",
            "2C": "200",
            "2D": "Gas Supply 2011",
            "3C": "CONTRACT",
            "3D": "Contracts",
            "4C": "",
            "4D": "",
            "5C": "ABACCH",
            "5D": "Bush, Aszam",
            "6C": "BRAD",
            "6D": "Jeffers, Brad",
            "7C": "",
            "7D": "",
            "ID": "5",
            "S": "37.4 KB",
            "I": "0",
            "AT": "1610647200",
            "CT": "1320948000",
            "UT": "1595466526",
            "PM": "\\\\#\\005\\20000\\200",
            "DN": "Terms and Conditions of QC (00001079-2x51615).DOC",
            "CHKOUT_TO_NAME": "QC User4 (QC4)",
            "List_ID": "x26BD9D8"
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
## JSON Failed CHECKIN Response

Note that when the response has failed, the `ErrorCount` value has a number, the `RCTX` value determines what the error is. The Worldox API always returns a `200` status even on failure.  
```
{
    "root": {
        "data": {
            "XN": "",
            "LN": "x22FD748",
            "RN": "1",
            "FN": "",
            "C": "",
            "PF": "",
            "V": "",
            "O": "",
            "1C": "",
            "1D": "",
            "2C": "",
            "2D": "",
            "3C": "",
            "3D": "",
            "4C": "",
            "4D": "",
            "5C": "",
            "5D": "",
            "6C": "",
            "6D": "",
            "7C": "",
            "7D": "",
            "ID": "",
            "S": "",
            "I": "",
            "AT": "",
            "CT": "",
            "UT": "",
            "PM": "",
            "DN": "",
            "CHKOUT_TO_NAME": "",
            "List_ID": "x22FD748"
        },
        "errorStatus": {
            "ErrorCount": "1",
            "wd_Error_RCID": "8740",
            "wd_Error_RCTX": "WDRC_SID_INVALID",
            "wd_Error_MSG": "WDRC_SID_INVALID",
            "wd_Error_VAR": "wd_SID",
            "wd_Error_VAL": "wsOXUqa07JvXT$2FeMdVXhXK1E54umind11YEv3o5A86ddFMyGHdjLP7Pvv4M$3Dn",
            "wd_Error_DOCID": "",
            "wd_Error_DOCNAME": "",
            "req_ID": "",
            "Error": [
                {
                    "wd_Error_RCID": "8740",
                    "wd_Error_RCTX": "WDRC_SID_INVALID",
                    "wd_Error_MSG": "WDRC_SID_INVALID",
                    "wd_Error_VAR": "wd_SID",
                    "wd_Error_VAL": "wsOXUqa07JvXT$2FeMdVXhXK1E54umind11YEv3o5A86ddFMyGHdjLP7Pvv4M$3Dn"
                }
            ]
        }
    }
}
```
