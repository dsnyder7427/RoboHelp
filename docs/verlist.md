---
layout: default
title: VERLIST
nav_order: 28
---

# VERLIST

The VERLIST command obtains the version list of a given file. It is a GET request.

## VERLIST Example

`{Worldox Web Domain}  + 'cgi-bin/wdwebcgi.exe?VERLIST+wd_SID=' + {Worldox Web User Session) + '+wd_List_ID='+ x.LID + '+Wd_List_RecNum=' + x.RN + '+html=/v4/filelist/fileList.json' + '+skip=0+take=100'`

## VERSLIST Parameters

`HTMLOnOK`

This is the page to return on a successful call to VERLIST.

`v4\filelist\fileList.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`HTMLOnFail`

This is the page to return on a failed VERLIST.

`v4\filelist\fileList.json`

`{Worldox Web Domain}` 
		
Is the domain name

`wd_SID`

Is the session ID

`{Worldox Web User Session)`

Is the variable

`wd_List_RecNum`

Is the record number of the files in the list that you want to check out.

`wd_List_ID`

Is the record number of a file from previous FINDFILES search. 

`Skip`

Is where you start. 0 is the value. 

`Take`

Is set to 500, which is the current default. Note: In the future, you can configure this to be a greater value. 

## JSON Successful VERLIST Response

Note that when the response is successful, the `ErrorCount` value is blank. 

```
{
    "root": {
        "errorStatus": {
            "List_ID": "x26BC398",
            "List_Count": "2",
            "ErrorCount": "",
            "wd_Error_RCID": "",
            "wd_Error_RCTX": "",
            "wd_Error_MSG": "",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "wd_Tab": "12201:Client Files\\20000\\200\\00001079.DOC",
            "wd_Title": "Client Files\\20000\\200\\00001079.DOC",
            "wd_Desc": "Client Files\\20000\\200\\00001079.DOC",
            "wd_Desc_Loc": "Version List: Client Files\\20000\\200\\00001079.DOC",
            "wd_Raw_Loc": "Version List: \\\\fs01\\worldox\\Data\\WDOX\\Clients\\20000\\200\\00001079.DOC",
            "wd_True_Loc": "Version List: \\\\fs01\\worldox\\Data\\WDOX\\Clients\\20000\\200\\00001079.DOC",
            "wd_Groupings": "0",
            "Error": ""
        },
        "data": [
            {
                "XN": "Terms and Conditions of QC",
                "FN": "00001079.doc",
                "UPD": "1544204492",
                "SZ": "37.9 KB",
                "VER": "1",
                "I": "0",
                "stFl": "5",
                "stIc": "0",
                "HASH": "xF83934A6",
                "FP": "\\\\#\\005\\20000\\200\\~VER\\1",
                "FPR": "\\\\#\\005\\20000\\200\\~VER\\1\\00001079.doc",
                "LN": "1",
                "RN": "2",
                "LID": "x26BC398",
                "F1C": "20000",
                "F1D": "City of Mesa",
                "F1N": "Client",
                "F2C": "200",
                "F2D": "Gas Supply 2011",
                "F2N": "Matter",
                "F3C": "CONTRACT",
                "F3D": "Contracts",
                "F3N": "DocType",
                "F5C": "ABACCH",
                "F5D": "Bush, Aszam",
                "F5N": "Author",
                "F6C": "BRAD",
                "F6D": "Jeffers, Brad",
                "F6N": "Typist",
                "ACC": "1595527200",
                "CRTD": "1320948000",
                "CBID": "5",
                "CBNM": "Client Files",
                "LOC": "Client Files\\20000\\200\\~VER\\1",
                "EXT": "DOC",
                "OW": "Demo User (DEMO81)",
                "GT": "DOC",
                "Name": "Terms and Conditions of QC (00001079-1x51615).DOC",
                "CHKOUT_TO_LINE": ""
            },
            {
                "XN": "Terms and Conditions of QC",
                "FN": "00001079.doc",
                "UPD": "1595466526",
                "SZ": "37.4 KB",
                "VER": "2",
                "I": "0",
                "stFl": "5",
                "stIc": "0",
                "HASH": "x95B47520",
                "FP": "\\\\#\\005\\20000\\200",
                "FPR": "\\\\#\\005\\20000\\200\\00001079.doc",
                "LN": "2",
                "RN": "1",
                "LID": "x26BC398",
                "F1C": "20000",
                "F1D": "City of Mesa",
                "F1N": "Client",
                "F2C": "200",
                "F2D": "Gas Supply 2011",
                "F2N": "Matter",
                "F3C": "CONTRACT",
                "F3D": "Contracts",
                "F3N": "DocType",
                "F5C": "ABACCH",
                "F5D": "Bush, Aszam",
                "F5N": "Author",
                "F6C": "BRAD",
                "F6D": "Jeffers, Brad",
                "F6N": "Typist",
                "ACC": "1609351200",
                "CRTD": "1320948000",
                "CBID": "5",
                "CBNM": "Client Files",
                "LOC": "Client Files\\20000\\200",
                "EXT": "DOC",
                "OW": "QC User10 (QC10)",
                "FF": "BB_HEART",
                "GT": "DOC",
                "Name": "Terms and Conditions of QC (00001079-2x51615).DOC",
                "CHKOUT_TO_LINE": ""
            }
        ]
    }
}
```

## JSON Failed VERLIST Response

Note that when the response has failed, the `ErrorCount` value has a number, the `RCTX` value determines what the error is. The Worldox API always returns a `200` status even on failure.  

```
{
    "root": {
        "errorStatus": {
            "List_ID": "x1B3BDC0",
            "List_Count": "",
            "ErrorCount": "1",
            "wd_Error_RCID": "8740",
            "wd_Error_RCTX": "WDRC_SID_INVALID",
            "wd_Error_MSG": "WDRC_SID_INVALID",
            "wd_Error_VAR": "wd_SID",
            "wd_Error_VAL": "1UkJs0Yx7WbAyO30UIOga9ZjeZOneBJULVF3nsfyHkx8ruEWEaDPvrFkuPs$3Dihoiguifuc",
            "wd_Tab": ":",
            "wd_Title": "",
            "wd_Desc": "",
            "wd_Desc_Loc": "",
            "wd_Raw_Loc": "",
            "wd_True_Loc": "",
            "wd_Groupings": "0",
            "Error": [
                {
                    "wd_Error_RCID": "8740",
                    "wd_Error_RCTX": "WDRC_SID_INVALID",
                    "wd_Error_MSG": "WDRC_SID_INVALID",
                    "wd_Error_VAR": "wd_SID",
                    "wd_Error_VAL": "1UkJs0Yx7WbAyO30UIOga9ZjeZOneBJULVF3nsfyHkx8ruEWEaDPvrFkuPs$3Dihoiguifuc"
                }
            ]
        },
        "data": [
            {
                "XN": "%:Xname%",
                "FN": "%:DOCID%",
                "UPD": "%:wUPDATED%",
                "SZ": "%:SIZE%",
                "CM": "%:COMMENTS%",
                "VER": "%:VERSION%",
                "I": "%:wSTATUSID%",
                "stFl": "%:wSTATUS_FLAGS%",
                "stIc": "%:wSTATUS_ICON%",
                "CAT_ID":%CATS_JSON%,
                "HASH": "%:H#%",
                "dwRC": "%:dwRC%",
                "FP": "%:UNCPG_PATHONLY%",
                "FPR": "%:UNCPG_PATHFILE%",
                "LN": "%:L#%",
                "RN": "%:R#%",
                "LID": "x1B3BDC0",
                "F1C": "%:FIELD1%",
                "F1D": "%:FIELD1DESC%",
                "F1N": "%:Field1Name%",
                "F2C": "%:FIELD2%",
                "F2D": "%:FIELD2DESC%",
                "F2N": "%:Field2Name%",
                "F3C": "%:FIELD3%",
                "F3D": "%:FIELD3DESC%",
                "F3N": "%:Field3Name%",
                "F4C": "%:FIELD4%",
                "F4D": "%:FIELD4DESC%",
                "F4N": "%:Field4Name%",
                "F5C": "%:FIELD5%",
                "F5D": "%:FIELD5DESC%",
                "F5N": "%:Field5Name%",
                "F6C": "%:FIELD6%",
                "F6D": "%:FIELD6DESC%",
                "F6N": "%:Field6Name%",
                "F7C": "%:FIELD7%",
                "F7D": "%:FIELD7DESC%",
                "F7N": "%:Field7Name%",
                "ACC": "%:wACCESSED%",
                "CRTD": "%:wCREATED%",
                "PathMap": "%:PATHMAP%",
                "CBID": "%:wGROUP%",
                "CBNM": "%:GROUP%",
                "LOC": "%:PATH%",
                "EXT": "%:EXT%",
                "OW": "%:OWNERINIT%",
                "FF": "%:FAVORITE%",
                "GT": "%:EXT%",
                "Name": "%:LONGNAME%",
                "szRC": "%:szRC%",
                "CHKOUT_TO_PREF": "%:CHKOUT_TO_PREF%",
                "CHKOUT_TO_NAME": "%:CHKOUT_TO_NAME%",
                "CHKOUT_ON_PREF": "%:CHKOUT_ON_PREF%",
                "CHKOUT_ON_DATE": "%:CHKOUT_ON_DATE%",
                "CHKOUT_TO_LINE": "%:CHKOUT_TO_LINE%"
            }
        ]
    }
}
```
