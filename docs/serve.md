---
layout: default
title: SERVE
nav_order: 20
---

# SERVE

The SERVE command returns a data list for the logged in user. Note: HASH and REREAD are SERVE commands. 

[SERVE Example](#serve-example)

[SERVE Parameters](#serve-parameters)

[SERVE Examples for Different Pages](#serve-examples-for-different-pages)

[JSON Successful SERVE Response](#json-successful-serve-response)

[JSON Failed SERVE Response](#json-failed-serve-response)

## SERVE Example

`{{url}}/cgi-bin/wdwebcgi.exe?SERVE&wd_SID={{session}}&html={{page}}`

## Parameters

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

### SetField.json FILEWDL (Update Temp WDL)

`/v4/fileActions/SetField.json`

	For a given list_ID and Recnum set metadata

#### Required parameters

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

### /v4/sideMenu/expandBranch.json

	`/v4/sideMenu/expandBranch.json`

	
	Returns the list of children within workspaces. 

`{{url}}/cgi-bin/wdwebcgi.exe?SERVE&wd_SID={{session}}&Wd_List_RecNum=1&html=/v4/sideMenu/expandBranch.json&wd_List_ID={{wkspId}}&dwRecNum=53715132&dwExpand=3
dwExpand`

	Is a parameter. The two values it can have are

`3` to expand the tree 

or

`5` to close the tree.

	For information about TREEVIEW (Workspace Parent), see the *TREEVIEW (Workspace Parent)* section. 
 
### sideMenu/favorites.json

	`/v4/sideMenu/favorites.json`
	
	Returns the list of Favorite File categories

### sideMenu/bookmarks.json

	`/v4/sideMenu/bookmarks.json`

	Returns the list of Bookmarks

### Favorite Matters

	`/v4/sideMenu/favMatters.json`

	This is the html parameter specified in the SERVE example at the beginning of this section. Returns the list of Favorite Matters.

### sideMenu/quickprofiles.json

	`/v4/sideMenu/quickprofiles.json`

	Returns the list of Quick Profiles for SaveAs

### templates/searchList.json

	`/v4/templates/searchList.json`

	Returns the list of Search Templates
### cabinets/folder-list.json

`/v4/cabinets/folder-list.json`

	Returns the subfolders of a given folder
	
#### Required parameters

`wd_BasePath`

### Set INI/iniSet.json

`/v4/ini/iniSet.json`

#### Required parameters

`szSection` INI section in question

`szINI` INI type
	
`szKey`

`szData` displays the number of files at the bottom of the file list in Worldox

## ini/iniRead.json (Get INI get section) 

`v4/ini/iniRead.json`

	Read from the Worldox.ini, WD$$$$$$.ini or wdhook/wduser.ini

#### Required parameters

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
