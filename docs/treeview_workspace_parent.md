---
layout: default
title: TREEVIEW Workspace Parent
nav_order: 24
---


# TREEVIEW WORKSPACE PARENT

The TREEVIEW (Workspace parent) command displays the side navigation pane. 

[TREEVIEW Example](#treeview-example)

[TREEVIEW Parameters](#treeview-parameters)

[JSON Successful TREEVIEW Response](#json-successful-treeview-response)

[JSON Failed TREEVIEW Response](#json-failed-treeview-response)

## TREEVIEW Example

`/cgi-bin/wdwebcgi.exe?TREEVIEW&wd_SID={{session}}`

## TREEVIEW Parameters

`wd_SID`

he Worldox session ID

Optional:

`wd_List_ID`

The Treeview to manipulate

`dwRecNUM`

Is the record number of a file from previous FINDFILES search. 

`dwExpand`

Is the branch to expand or collapse 

`3` returns the content of the child

`5` returns to the (Workspace) parent and collapses the branch

```
WDAPI_TREEBRANCH_FLAG_REFRESH	0x0001 // Rebuilds the RecTbl from dwRecNum (0 == Root)
WDAPI_TREEBRANCH_FLAG_EXPAND	0x0002
WDAPI_TREEBRANCH_FLAG_COLLAPSE	0x0004
```


To get the target branch: Pass in `_REFRESH and _EXPAND`

To get the parent: Do a `_COLLAPSE and _REFRESH`

`HTML`

`/v4/sideMenu/workspacesRoot.json` builds the root Workspace tree

`/v4/sideMenu/expandBranch.json` expands the current branch based on the record number and list ID

## JSON Successful TREEVIEW Response

Note that when the response is successful, the ErrorCount value is blank. 

```
{
    "root": {
        "errorStatus": {
            "List_ID": "x26BBDE0",
            "List_Count": "12",
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
                "Line#": "1",
                "Rec#": "52026876",
                "Level": "2",
                "Flags": "1",
                "Text": "<Recent Projects>",
                "Draw": "<Recent Projects>",
                "TypeID": "WDL_PATH",
                "Path": ""
            },
            {
                "Line#": "2",
                "Rec#": "52030412",
                "Level": "2",
                "Flags": "1",
                "Text": "Aguilar, Alex",
                "Draw": "Aguilar, Alex",
                "TypeID": "WDL_PATH",
                "Path": "\\\\#\\006\\AAGUIL"
            },
            {
                "Line#": "3",
                "Rec#": "52028332",
                "Level": "2",
                "Flags": "1",
                "Text": "City of Mesa - General",
                "Draw": "City of Mesa - General",
                "TypeID": "WDL_PATH",
                "Path": "\\\\#\\005\\20000\\100"
            },
            {
                "Line#": "4",
                "Rec#": "52018468",
                "Level": "2",
                "Flags": "1",
                "Text": "Client Files\\00042\\0010",
                "Draw": "Client Files\\00042\\0010",
                "TypeID": "WDL_PATH",
                "Path": "\\\\#\\005\\00042\\0010"
            },
            {
                "Line#": "5",
                "Rec#": "52015140",
                "Level": "2",
                "Flags": "1",
                "Text": "Corporate General Counsel\\ADMIN\\ACCT\\0193",
                "Draw": "Corporate General Counsel\\ADMIN\\ACCT\\0193",
                "TypeID": "WDL_PATH",
                "Path": "\\\\fs01\\worldox\\Data\\WDOX\\CORPGC\\ADMIN\\ACCT\\0193"
            },
            {
                "Line#": "6",
                "Rec#": "52026044",
                "Level": "2",
                "Flags": "1",
                "Text": "Credit Forms",
                "Draw": "Credit Forms",
                "TypeID": "WDL_PATH",
                "Path": "\\\\#\\003\\CRED"
            },
            {
                "Line#": "7",
                "Rec#": "52030620",
                "Level": "2",
                "Flags": "1",
                "Text": "Development\\ENDOW\\1\\100",
                "Draw": "Development\\ENDOW\\1\\100",
                "TypeID": "WDL_PATH",
                "Path": "\\\\fs01\\worldox\\Data\\WDOX\\Dev\\ENDOW\\1\\100"
            },
            {
                "Line#": "8",
                "Rec#": "52023756",
                "Level": "2",
                "Flags": "1",
                "Text": "Development\\ESTATE\\1\\110",
                "Draw": "Development\\ESTATE\\1\\110",
                "TypeID": "WDL_PATH",
                "Path": "\\\\fs01\\worldox\\Data\\WDOX\\Dev\\ESTATE\\1\\110"
            },
            {
                "Line#": "9",
                "Rec#": "52028124",
                "Level": "2",
                "Flags": "1",
                "Text": "Display Producers -  fifth ave purchase",
                "Draw": "Display Producers -  fifth ave purchase",
                "TypeID": "WDL_PATH",
                "Path": "\\\\#\\005\\00060\\0140"
            },
            {
                "Line#": "10",
                "Rec#": "54462548",
                "Level": "2",
                "Flags": "1",
                "Text": "Real Estate\\100\\1\\100",
                "Draw": "Real Estate\\100\\1\\100",
                "TypeID": "WDL_PATH",
                "Path": "\\\\fs01\\worldox\\Data\\WDOX\\RE\\100\\1\\100"
            },
            {
                "Line#": "11",
                "Rec#": "52023340",
                "Level": "2",
                "Flags": "1",
                "Text": "Tawfik, Harry D MD",
                "Draw": "Tawfik, Harry D MD",
                "TypeID": "WDL_PATH",
                "Path": "\\\\#\\005\\00102\\0020"
            },
            {
                "Line#": "12",
                "Rec#": "52031036",
                "Level": "2",
                "Flags": "1",
                "Text": "wscadmin",
                "Draw": "wscadmin",
                "TypeID": "WDL_PATH",
                "Path": "\\\\#\\006\\WSCADMIN"
            }
        ]
    }
}
```

## JSON Failed TREEVIEW Response

Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  

```
{
    "root": {
        "errorStatus": {
            "List_ID": "null",
            "List_Count": "",
            "ErrorCount": "1",
            "wd_Error_RCID": "8740",
            "wd_Error_RCTX": "WDRC_SID_INVALID",
            "wd_Error_MSG": "WDRC_SID_INVALID",
            "wd_Error_VAR": "wd_SID",
            "wd_Error_VAL": "jD7TvH6VVoSZSTYJsyoVLs8xFfkMe0jEiHdnWU1DOjMuKigodghCfMtfWGY$3Dljohooi",
            "Error": [
                {
                    "wd_Error_RCID": "8740",
                    "wd_Error_RCTX": "WDRC_SID_INVALID",
                    "wd_Error_MSG": "WDRC_SID_INVALID",
                    "wd_Error_VAR": "wd_SID",
                    "wd_Error_VAL": "jD7TvH6VVoSZSTYJsyoVLs8xFfkMe0jEiHdnWU1DOjMuKigodghCfMtfWGY$3Dljohooi"
                }
            ]
        },
        "data": [
            {
                "Line#": "%:L#%",
                "Rec#": "%:R#%",
                "Level": "%:Level%",
                "Flags": "%:Flags%",
                "Text": "%:TEXT%",
                "Draw": "%:DRAW%",
                "TypeID": "%:TypeID%",
                "Path": "%:PATH%"
            }
        ]
    }
}
```

