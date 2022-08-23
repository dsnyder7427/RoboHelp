---
layout: default
title: SERVE
nav_order: 20
---

# SERVE

The SERVE command returns a data list for the logged in user. **Note:** HASH and REREAD are SERVE commands. 


[SERVE Example](#serve-example)

[SERVE Parameters](#serve-parameters)

[SERVE Examples for Different Pages](#serve-examples-for-different-pages)

[JSON Successful SERVE Response](#json-successful-serve-response)

[JSON Failed SERVE Response](#json-failed-serve-response)

[Create a Temporary WDL File](#create-a-temporary-wdl-file)

[Download a Temporary WDL File](#download-a-temporary-wdl-file)

[JSON Successful Download Output for a Temporary WDL File](#json-successful-download-output-for-a-temporary-wdl-file)


## SERVE Example
<!-- {% raw %} -->
`{{url}}/cgi-bin/wdwebcgi.exe?SERVE&wd_SID={{session}}&html={{page}}`
<!-- {% endraw %} -->

## SERVE Parameters

`HTML`
	
This is the page to be served.
	
`\v4\filelist\rereadrecord.json`
	
Pass in

Take 1

`Skip`

Is the offset of the list
		
`wd_List_RecNum`

The recnum of file

`wd_List_ID`

Is the list ID of file
	
## SERVE Examples for Different Pages

There are many different pages that can be served. Please note while reading the following examples that some of these pages have additional parameters and others do not.

**SetField.json FILEWDL (Update Temp WDL)**

`/v4/fileActions/SetField.json`

For a given list_ID and Recnum set metadata

**Required parameters**

`wd_List_ID, wd_List_RecNum, nElemId, szData`

The FILEWDL command adds or removes a file from the .wdl project.

`wd_list_ID`

Is the list ID of a project

`wd_SID`
	
Is the Worldox session ID

`Html1`

Should be /v4/errorlog/error.json or something similar since the API will only return whether it worked or not

`wd_List_RecNum`

Is the existing record number of an item in the wdl if you want to remove it. If there is no RecNum, use -1. 

`wd_File_PathFile_Value`
	
Is the file to add

`nElemID`

Is the file’s element ID

`szData`

**/v4/sideMenu/expandBranch.json**

`/v4/sideMenu/expandBranch.json`

Returns the list of children within workspaces. 

`{{url}}/cgi-bin/wdwebcgi.exe?SERVE&wd_SID={{session}}&Wd_List_RecNum=1&html=/v4/sideMenu/expandBranch.json&wd_List_ID={{wkspId}}&dwRecNum=53715132&dwExpand=3
dwExpand`

Is a parameter. The two values it can have are

`3` to expand the tree 

or

`5` to close the tree.

For information about TREEVIEW (Workspace Parent), see the [TREEVIEW (Workspace Parent)](https://dsnyder7427.github.io/Worldox-Web-API/treeview_workspace_parent.html) section. 

**sideMenu/favorites.json**

`/v4/sideMenu/favorites.json`
		
Returns the list of Favorite File categories

**sideMenu/bookmarks.json**

`/v4/sideMenu/bookmarks.json`

Returns the list of Bookmarks

**Favorite Matters**

`/v4/sideMenu/favMatters.json`

This is the html parameter specified in the SERVE example at the beginning of this section. Returns the list of Favorite Matters.

**sideMenu/quickprofiles.json**

`/v4/sideMenu/quickprofiles.json`

Returns the list of Quick Profiles for SaveAs

**templates/searchList.json**

`/v4/templates/searchList.json`

Returns the list of Search Templates

**cabinets/folder-list.json**

`/v4/cabinets/folder-list.json`

Returns the subfolders of a given folder
	
**Required parameters**

`wd_BasePath`

**Set INI/iniSet.json**

`/v4/ini/iniSet.json`

**Required parameters**

`szSection` INI section in question

`szINI` INI type
	
`szKey`

`szData` displays the number of files at the bottom of the file list in Worldox

**ini/iniRead.json (Get INI get section)**

`v4/ini/iniRead.json`

Read from the Worldox.ini, WD$$$$$$.ini or wdhook/wduser.ini

**Required parameters**

`szSection` INI section in question

`szINI` INI type

`szKey`

### ini/iniReadKey.json (Get INI with key) 

`/v4/ini/iniReadKey.json`

Read from the Worldox.ini, WD$$$$$$.ini or wdhook/wduser.ini

#### Required parameters

`szSection` INI section in question (For example, vtabTree)

`szINI` INI type

`szKey`

### /v4/errorLog/getVar.json

`/v4/errorLog/getVar.json&szVar={{ wd_Error_RCTX }}&wd_USER_CODE_ISO2={{ Language Code }}`

The `wd_Error_RCTX` is the error identifier from the previous failed request.

The Language Code is the language the text should be in.

Currently the Language Code only passes US English so the value should be “us”. 

Here is an example of an Error when doing a NewFile.
   
   ```
   
   "errorStatus": {
        "ErrorCount": "1",
        "wd_Error_RCID": "8158",
        "wd_Error_RCTX": "WDRC_XFERFILE_FAIL_CONNECT",
        "wd_Error_MSG": "WDRC_XFERFILE_FAIL_CONNECT",
        "wd_Error_VAR": "",
        "wd_Error_VAL": ""
    }
   
   ```
    
### filelist/rereadrecord.json (Hash, Reread File) 

**Note:** HASH and REREAD FILE have the same output

`\v4\filelist\rereadrecord.json`

Pass in

Take 1

Skip

s the offset of the list

`wd_List_RecNum`

The recnum of file

`wd_List_ID`

Is the list ID of file

### filterlist/filterlist.json 

`/v4/filterlist/filterList.json`

### expandBranch.json (TREEOPEN, Workspace children)

`/v4/sideMenu/expandBranch.json`

#### Required parameters

`szSection` INI section in question

`szINI` INI type

`szKey`

`3` returns the content of the child

`5` returns to the (Workspace) parent and collapses the branch

### GetRights/userRights.json

`/v4/authentication/userRights.json`

### GetVar/getVar.json

`/v4/errorLog/getVar.json`

#### Required parameters

`szVar` Error section that user needs txt from

`wd_USER_CODE_ISO2` language country code

### UploadAgent/uploadAgent.json

`/v4/wdAgent/uploadAgent.json`

## JSON Successful SERVE Response

Reread File was used for this successful SERVE example in JSON.

Note that when the response is successful, the ErrorCount value is blank. 

```
{
    "root": {
        "errorStatus": {
            "List_ID": "x26BC0D0",
            "List_Count": "23",
            "ErrorCount": "",
            "wd_Error_RCID": "",
            "wd_Error_RCTX": "",
            "wd_Error_MSG": "",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "wd_Tab": "10613:All",
            "wd_Title": "All",
            "wd_Desc": "Favorite Files",
            "wd_Desc_Loc": "Favorite Files",
            "wd_Raw_Loc": "Favorite Files",
            "wd_True_Loc": "Favorite Files",
            "wd_List_Count_ALL": "23",
            "wd_List_Count_XML": "23",
            "wd_Groupings": "0"
        },
        "data": [
            {
                "XN": "2001 natural gas forecast",
                "FN": "00001197.msg",
                "UPD": "1490727048",
                "SZ": "18.4 KB",
                "I": "0",
                "stFl": "5",
                "stIc": "0",
                "HASH": "xF2BB3F5D",
                "FPR": "\\\\#\\005\\00060\\0140\\00001197.msg",
                "LN": "1",
                "RN": "18",
                "LID": "x26BC0D0",
                "F1C": "00060",
                "F1D": "Display Producers",
                "F1N": "Client",
                "F2C": "0140",
                "F2D": "Fifth Ave Real Estate Purchase",
                "F2N": "Matter",
                "F3C": "AGR",
                "F3D": "Agreement",
                "F3N": "DocType",
                "F5C": "RYAN",
                "F5D": "Mosto, Ryan",
                "F5N": "Author",
                "F6C": "RYAN",
                "F6D": "Mosto, Ryan",
                "F6N": "Typist",
                "ACC": "1556647200",
                "CRTD": "978372000",
                "CBID": "5",
                "CBNM": "Client Files",
                "LOC": "Client Files\\00060\\0140",
                "EXT": "MSG",
                "OW": "Demo User (DEMO22)",
                "FF": "BB_HEART",
                "GT": "MSG",
                "Name": "2001 natural gas forecast (00001197x51615).MSG",
                "PSD": "<undefined>"
            }
        ]
    }
}
```

## JSON Failed SERVE Response

Reread File was used for this failed SERVE example in JSON.

Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  

```
{
    "root": {
        "errorStatus": {
            "List_ID": "x26BC0D0",
            "List_Count": "",
            "ErrorCount": "1",
            "wd_Error_RCID": "8740",
            "wd_Error_RCTX": "WDRC_SID_INVALID",
            "wd_Error_MSG": "WDRC_SID_INVALID",
            "wd_Error_VAR": "wd_SID",
            "wd_Error_VAL": "WLgaeeJYQElNZIurVAp7ckZ6ocruWU0crN4RRny07ShkouEiOIKcd$2FPQDlo$3Dshrshr",
            "wd_Tab": ":",
            "wd_Title": "",
            "wd_Desc": "",
            "wd_Desc_Loc": "",
            "wd_Raw_Loc": "",
            "wd_True_Loc": "",
            "wd_List_Count_ALL": "",
            "wd_List_Count_XML": "",
            "wd_Groupings": "0"
        },
        "data": [
            {
                "XN": "%:Xname%",
                "FN": "%:DOCID%",
                "UPD": "%:wUPDATED%",
                "SZ": "%:SIZE%",
                "CM": "%:COMMENTS%",
                "VER": "%:VERSION%",
                "dwRC": "%:dwRC%",
                "I": "%:wSTATUSID%",
                "stFl": "%:wSTATUS_FLAGS%",
                "stIc": "%:wSTATUS_ICON%",
                "CAT_ID":%CATS_JSON%,
                "HASH": "%:H#%",
                "FPR": "%:UNCPG_PATHFILE%",
                "LN": "%:L#%",
                "RN": "%:R#%",
                "LID": "x26BC0D0",
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
                "CHKOUT_TO_LINE": "%:CHKOUT_TO_LINE%",
                "PSL": "%:SHARED_LINK%",
                "PSU": "%:SHARED_USER%",
                "PSD": "%:SHARED_DATE%"
            }
        ]
    }
}
```


## Create a Temporary WDL File

To create a temporary WDL file, you must perform the following steps in order.

1. Login (if your session has ended). If necessary, see LOGON for details.
2. Send OPENWDL. For details, see OPENWDL (Create Temp WDL).
3. Send FINDFILES to create a temporary list (Create Temp List). (FINDFILES is used for the Get List SERVE command.) You will need the List ID from Create Temp List output. For details, see FINDFILES (Get List, Create Temp List, SORTFILES).
4. Use the SERVE command, FILEWDL Update Temp WDL.  For details, see SetField.json FILEWDL (Update Temp WDL). 


## Download a Temporary WDL File

1. Login (if your session has ended). If necessary, see LOGON for details.
2. Send OPENWDL. For details, see OPENWDL (Create Temp WDL).
3. Send FINDFILES to create a temporary list (Create Temp List). (FINDFILES is used for the Get List SERVE command.) You will need the List ID from Create Temp List output. For details, see FINDFILES (Get List, Create Temp List, SORTFILES).
4. Use the SERVE command, FILEWDL Update Temp WDL.  For details, see SetField.json FILEWDL (Update Temp WDL). 
5. Send DOWNLOAD. For details, see DOWNLOAD. Note: Pass a RecNum of -1 if there is no record number.

## JSON Successful Download Output for a Temporary WDL File

```
{
    "root": {
        "data": {
            "fileLoc": "/cgi-bin/WDSIDS/E7V216TmlZQGnwR7aZWDKOp9BI1hdDehU%242Bd9FK1I5YQlx2sR5UZ%242F%242BeIPz4Q%243D/OPEN/Temp%20wdl%20from%20postman.WDL",
            "FileNme": "",
            "FileZMS": ""
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
