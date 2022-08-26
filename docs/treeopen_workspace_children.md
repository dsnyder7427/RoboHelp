---
layout: default
title: TREEOPEN Workspace Children
nav_order: 23
---

# TREEOPEN (WORKSPACE CHILDREN) 

The TREEOPEN command expands a branch of a parent child list. Please also see `/v4/sideMenu/expandBranch.json` in the *SERVE Examples for Different Pages* section for [SERVE](https://dsnyder7427.github.io/Worldox-Web-API/serve.html).

[TREEOPEN Example](#treeopeon-example)

[TREEOPEN Parameters](#treeopen-parameters)

Do the following steps before you can send a TREEOPEN command.
1.	Send TREEVIEW. This will return a list of Workspaces and a List ID which will needed for TREEOPEN. See [TREEVIEW Workspace Parent](https://dsnyder7427.github.io/Worldox-Web-API/treeview_workspace_parent.html) for details.
2.	Send a SERVE command. This will return a list of Projects inside of the selected Workspace. Each Project has a RecNum that is needed for TREEOPEN.
3.	Send TREEOPEN. This will return all the files inside of the Project.

## TREEOPEN Example

**Note:** `TREEOPEN` has the same output as `FINDFILES`. 

`https://phoenix.wdsaas.com/cgi-bin/wdwebcgi.exe?TREEOPEN+wd_SID=2d5WUGkZVc8er4fgFbLFDWgSdNhr8w0T3Ui1I5IDdehd00rDFdmJqriiM7Y%243D+html=/v4/filelist/fileList.json+wd_List_RecNum=27085036+wd_List_ID=x145EA08+wd_List_Flags=0+skip=0+take=100+Wd_File_Sort_Key1=5380+wd_File_Sort_Dir1=0`

## TREEOPEN Parameters

Required parameters passed in TreeOpen are:

`wd_SID`

Is the session ID 

`HTMLOnOK`

This is the page to return on a successful call to FINDFILES.

`v4\filelist\fileList.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`HTMLOnFail`

This is the page to return on a failed FINDFILES.

`v4\filelist\fileList.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`wd_List_RecNum`

s the record number of the files in the list that you want to open in a tree . This is the RecNum (record number) from the SERVE command in step 2 in TREEOPEN (Workspace Children).

`wd_List_ID`

This is the List ID from TREEVIEW Step 1 as described in TREEOPEN (Workspace Children).

`wd_List_Flags=0`
	
List ID flag (indicates if the file list has flags). 

`Skip`
	
Is where you start. 0 is the value. 

`Take`

Is set to 500, which is the current default. Note: In the future, you can configure this to be a greater value. 
