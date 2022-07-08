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

[SetField.json FILEWDL (Update Temp WDL)](#setfield.json-filewdl-update-temp-wdl)

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

