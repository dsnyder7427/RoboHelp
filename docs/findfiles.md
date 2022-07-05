---
layout: default
title: FINDFILES
nav_order: 11
---

# FINDFILES (GET LIST, CREATE TEMP LIST, SORTFILES)

The FINDFILES command is the Worldox search command. It is a GET request. It is sometimes referred to as GetList. Note: FINDFILES is used for GetList and Create Temp list. SORTFILES is a separate command, but it can use the same output as FINDFILES.

[FINDFILES Example](#findfiles-example)

[FINDFILES Parameters](#findfiles-parameters)

[FINDFILES Sort Values](#findfiles-sort-values)

[JSON Response Keys for FINDFILES](#json-response-keys-for-findfiles)

[JSON Response Keys for FINDFILES](#json-response-keys-for-findfiles)

[JSON Successful FINDFILES Response](#json-successful-findfiles-response)

[Note About Successful JSON FINDFILES Response](#note-about-sucessful-json-findfiles-response)

[JSON Failed FINDFILES Response](#json-failed-findfiles-response)

## FINDFILES Example

`{{url}}/cgi-bin/wdwebcgi.exe?FINDFILES&wd_SID={{session}}&html=/v4/filelist/fileList.json&wd_FIND_QUERY={{findQuery}}&skip=&{{skip}}&take={{take}}`

## FINDFILES Parameters	
`HTMLOnOK`
This is the page to return on a successful call to FINDFILES.
`v4\filelist\fileList.json`
**Note:** 'api' is deprecated but still can be used. Going forward v4 is the best practice.
`HTMLOnFail`
This is the page to return on a failed FINDFILES.
`v4\filelist\fileList.json`
**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.
`wd_FIND_QUERY`
Is the search used in the session authenticated to the URL
`Skip`
	Is where you start. 0 is the value. 
`Take`
Is set to 500, which is the current default. Note: In the future, you can configure this to be a greater value. 


## FINDFILES Sort Values
`wd_file_sort_key1`
Is whatever the column ID is
`wd_file_sort_dir1`
	`1` sorts the column in descending order
	`0` sorts the column in ascending order
`wd_File_Updated_Value`
`wd_File_Version_Value`
`wd_File_Size_Value`
`wd_File_Xname_Value`
`wd_File_FileName_Value`

## JSON Response Keys for FINDFILES

The following table describes the available flags for `wd_List_Rename_Flags`.

| **JSON Key** | **Slim Parameter** | **Meaning** |
| --- | --- | --- |
| &quot;Description&quot; | &quot;%Xname%&quot;, | File description |
| --- | --- | --- |
| &quot;DocId&quot; | &quot;%DOCID%&quot;,  | File name |
| &quot;DateUpdated&quot;, | &quot;%wUPDATED%&quot;, | unixtimestamp of date updated |
| &quot;Size&quot;, | &quot;%SIZE%&quot;, | File size |
| &quot;Comments&quot;, | &quot;%COMMENTS%&quot;, | File comments |
| &quot;Version&quot;, | &quot;%VERSION%&quot;, | Version number |
| &quot;I&quot;, | &quot;%wSTATUSID%&quot;, | Numerical value of file status (checked-out etc.) |
| &quot;dwRC&quot;, | &quot;%dwRC%&quot;, | Return code of the file (if it is missing from the file system) |
| &quot;stFl&quot;, | &quot;%wSTATUS\_FLAGS%&quot;, | Status flags # |
| &quot;stIc&quot;, | &quot;%wSTATUS\_ICON%&quot;, | Status icon # |
| &quot;HASH&quot;, | &quot;%H#%&quot;, | Hash of every value above it |
| &quot;FilePath&quot;, | &quot;%UNCPG\_PATHONLY%&quot;, | Descriptive path of file |
| &quot;FilePathReal&quot;, | &quot;%UNCPG\_PATHFILE%&quot;, | Physical path of file |
| &quot;LN&quot;, | &quot;%L#%&quot;, | File offset |
| &quot;RN&quot;, | &quot;%R#%&quot;, | File record number |
| &quot;LID&quot;, | &quot;^wd\_List\_ID^&quot;, | List ID of current list |
| &quot;Field1&quot;, | &quot;%FIELD1%&quot;, | Field 1 code |
| &quot;Field1Desc&quot;, | &quot;%FIELD1DESC%&quot;, | Field 1 description |
| &quot;Field1Name&quot;, | &quot;%Field1Name%&quot;, | Field 1 name |
| &quot;Field2&quot;, | &quot;%FIELD2%&quot;, | Field 2 code |
| &quot;Field2Desc&quot;, | &quot;%FIELD2DESC%&quot;, | Field 2 description |
| &quot;Field2Name&quot;, | &quot;%Field2Name%&quot;, | Field 2 name |
| &quot;Field3&quot;, | &quot;%FIELD3%&quot;, | Field 3 code |
| &quot;Field3Desc&quot;, | &quot;%FIELD3DESC%&quot;, | Field 3 description |
| &quot;Field3Name&quot;, | &quot;%Field3Name%&quot;, | Field 3 name |
| &quot;Field4&quot;, | &quot;%FIELD4%&quot;, | Field 4 code |
| &quot;Field4Desc&quot;, | &quot;%FIELD4DESC%&quot;, | Field 4 description |
| &quot;Field4Name&quot;, | &quot;%Field4Name%&quot;, | Field 4 name |
| &quot;Field5&quot;, | &quot;%FIELD5%&quot;, | Field 5 code |
| &quot;Field5Desc&quot;, | &quot;%FIELD5DESC%&quot;, | Field 5 description |
| &quot;Field5Name&quot;, | &quot;%Field5Name%&quot;, | Field 5 name |
| &quot;Field6&quot;, | &quot;%FIELD6%&quot;, | Field 6 code |
| &quot;Field6Desc&quot;, | &quot;%FIELD6DESC%&quot;, | Field 6 description |
| &quot;Field6Name&quot;, | &quot;%Field6Name%&quot;, | Field 6 name |
| &quot;Field7&quot;, | &quot;%FIELD7%&quot;, | Field 7 code |
| &quot;Field7Desc&quot;, | &quot;%FIELD7DESC%&quot;, | Field 7 description |
| &quot;Field7Name&quot;, | &quot;%Field67Name%&quot;, | Field 7 name |
| &quot;AccessedDate&quot;, | &quot;%wACCESSED%&quot;, | unix timestamp of date accessed |
| &quot;DateCreated&quot;, | &quot;%wCREATED%&quot;, | unix timestamp of date created |
| &quot;PathMap&quot;, | &quot;%PATHMAP%&quot;, | &quot;Hidden&quot; path of file |
| &quot;ProfileGroupId&quot;, | &quot;%wGROUP%&quot;, | Cabinet ID |
| &quot;Cabinet&quot;, | &quot;%GROUP%&quot;, | Cabinet name |
| &quot;Location&quot;, | &quot;%PATH%&quot;, | Descriptive path |
| &quot;Extension&quot;, | &quot;%EXT%&quot;, | File extension |
| &quot;OW&quot;, | &quot;%OWNERINIT%&quot;, | Owner initials (last person to access the file |
| &quot;FF&quot;, | &quot;%FAVORITE%&quot;, | Is this file a favorite? If so, how? |
| &quot;EFR&quot;, | &quot;%EMAIL\_FR%&quot;, | Email was from |
| &quot;ETO&quot;, | &quot;%EMAIL\_TO%&quot;, | Email was to |
| &quot;ECC&quot;, | &quot;%EMAIL\_CC%&quot;, | Email had CC |
| &quot;EBC&quot;, | &quot;%EMAIL\_BCC%&quot;, | Email had bcc |
| &quot;ETS&quot;, | &quot;%EMAIL\_tSENT%&quot;, | Time email was sent |
| &quot;ETR&quot;, | &quot;%EMAIL\_tRCVD%&quot;, | Time email was received |
| &quot;ERF&quot;, | &quot;%EMAIL\_tRFDATE%&quot;, | Received from date |
| &quot;ERW&quot;, | &quot;%EMAIL\_RFWHO%&quot;, | Received from person |
| &quot;EAD&quot;, | &quot;%EMAIL\_ADDR%&quot;, | Email from |
| &quot;szRC&quot;, | &quot;%szRC%&quot;, | dwRCs error text |
| &quot;CHKOUT\_TO\_PREF&quot;, | &quot;%CHKOUT\_TO\_PREF%&quot;, | Part of the checked-out line |
| &quot;CHKOUT\_TO\_NAME&quot;, | &quot;%CHKOUT\_TO\_NAME%&quot;, | Part of the checked-out line |
| &quot;CHKOUT\_ON\_PREF&quot;, | &quot;%CHKOUT\_ON\_PREF%&quot;, | Part of the checked-out line |
| &quot;CHKOUT\_ON\_DATE&quot;, | &quot;%CHKOUT\_ON\_DATE%&quot;, | Part of the checked-out line |
| &quot;CHKOUT\_TO\_LINE&quot;, | &quot;%CHKOUT\_TO\_LINE%&quot;, | Full checked out-line |

## JSON Successful FINDFILES Response

Note that when the response is successful, the ErrorCount value is blank. 

```
{
    "root": {
        "errorStatus": {
            "List_ID": "x2304DA0",
            "List_Count": "3",
            "ErrorCount": "",
            "wd_Error_RCID": "",
            "wd_Error_RCTX": "",
            "wd_Error_MSG": "",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "wd_Tab": "10602:Find: Name=Excel ...",
            "wd_Type": "10602",
            "wd_Title": "Find: Name=Excel ...",
            "wd_Desc": "Find: Name=Excel; using Quick Access <Active>",
            "wd_Desc_Loc": "Find: Name=Excel; using Quick Access <Active>",
            "wd_Raw_Loc": "?E Excel | ?G 14;5;3;18;6 ?R D ?@Quick Access",
            "wd_True_Loc": "?E Excel | ?G 14;5;3;18;6 ?R D ?@Quick Access",
            "wd_Groupings": "0"
        },
        "data": [
            {
                "XN": "<span class='selectedTxt'>Excel</span> test.",
                "FN": "00015655.xlsx",
                "UPD": "1587490528",
                "LSZ": "8.6 KB",
                "I": "0",
                "stFl": "5",
                "stIc": "0",
                "HASH": "x3357286E",
                "EXT": "XLSX",
                "LN": "1",
                "RN": "3",
                "CBID": "5",
                "FP": "\\\\#\\005\\00001\\0010",
                "CRTD": "1587492000",
                "ACC": "1594663200",
                "FPR": "\\\\#\\005\\00001\\0010\\00015655.xlsx",
                "PSD": "<undefined>"
            },
            {
                "XN": "<span class='selectedTxt'>Excel</span> test.",
                "FN": "00015661.xlsx",
                "UPD": "1587490528",
                "LSZ": "8.6 KB",
                "CM": "Copied.",
                "I": "0",
                "stFl": "5",
                "stIc": "0",
                "HASH": "xAF06FCA3",
                "EXT": "XLSX",
                "LN": "2",
                "RN": "2",
                "CBID": "5",
                "FP": "\\\\#\\005\\00001\\0050",
                "CRTD": "1587492000",
                "ACC": "1587492000",
                "FPR": "\\\\#\\005\\00001\\0050\\00015661.xlsx",
                "PSD": "<undefined>"
            },
            {
                "XN": "Sutter <span class='selectedTxt'>Excel</span> Doc",
                "FN": "00015577.xlsx",
                "UPD": "1584985444",
                "LSZ": "8.3 KB",
                "I": "0",
                "stFl": "5",
                "stIc": "0",
                "HASH": "x11E76B0C",
                "EXT": "XLSX",
                "LN": "3",
                "RN": "1",
                "CBID": "5",
                "FP": "\\\\#\\005\\00007\\0050",
                "CRTD": "1584986400",
                "ACC": "1584986400",
                "FPR": "\\\\#\\005\\00007\\0050\\00015577.xlsx",
                "PSD": "<undefined>"
            }
        ]
    }
}
```
## Note about Successful JSON (FINDFILES) Response
Successful JSON output for FINDFILES can sometimes show an ErrorCount of 1 if no data is returned. FINDFILES is used for folders, templates, Favorites, filters and projects (WDL files). 
The following example shows that a WDL was created. It is still successful output even though an error says, wd_Error_RCTX": "WDRC_ZERO_PROJECT_CLEAN. In this case, there are no files in the project.

  ```
  {
    "root": {
        "errorStatus": {
            "List_ID": "x257A1C8",
            "List_Count": "0",
            "ErrorCount": "1",
            "wd_Error_RCID": "9105",
            "wd_Error_RCTX": "WDRC_ZERO_PROJECT_CLEAN",
            "wd_Error_MSG": "Empty Project List\nYour project contains no files.\n\n\n\n\nProjectCollection, wdInfo\nWarning, wdWarningIco\n\nOk",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "wd_Tab": "12011:New Project",
            "wd_Title": "New Project",
            "wd_Desc": "New Project",
            "wd_Desc_Loc": "Project: New Project",
            "wd_Raw_Loc": "Project: C:\\Users\\QC4@WORLDOXQC.COM\\AppData\\Local\\Temp\\WBGX\\4736.2\\$WD89F008955FFCBC950000008D.WDL",
            "wd_True_Loc": "Project: C:\\Users\\QC4@WORLDOXQC.COM\\AppData\\Local\\Temp\\WBGX\\4736.2\\$WD89F008955FFCBC950000008D.WDL",
            "wd_Groupings": "0",
            "Error": [
                {
                    "wd_Error_RCID": "9105",
                    "wd_Error_RCTX": "WDRC_ZERO_PROJECT_CLEAN",
                    "wd_Error_MSG": "Empty Project List\nYour project contains no files.\n\n\n\n\nProjectCollection, wdInfo\nWarning, wdWarningIco\n\nOk",
                    "wd_Error_VAR": "",
                    "wd_Error_VAL": ""
                }
            ]
        },
        "data": ""
    }
}
  ```

## JSON Failed FINDFILES Response
  
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
            "wd_Error_VAL": "YBWCWEmb24t19GDpPWf9VZwfrTxOBgbaG7JK5H8culn6nD$2Fk1hSqwabPijk$3Dn",
            "wd_Tab": ":",
            "wd_Type": "",
            "wd_Title": "",
            "wd_Desc": "",
            "wd_Desc_Loc": "",
            "wd_Raw_Loc": "",
            "wd_True_Loc": "",
            "wd_Groupings": "0"
        },
        "data": [
            {
                "XN": "%:Xname%",
                "FN": "%:DOCID%",
                "UPD": "%:wUPDATED%",
                "LSZ": "%:SIZE%",
                "CM": "%:COMMENTS%",
                "VER": "%:VERSION%",
                "I": "%:wSTATUSID%",
                "dwRC": "%:dwRC%",
                "stFl": "%:wSTATUS_FLAGS%",
                "stIc": "%:wSTATUS_ICON%",
                "CAT_ID": "%:CATS_JSON%",
                "HASH": "%:H#%",
                "FF": "%:FAVORITE%",
                "EXT": "%:EXT%",
                "LN": "%:L#%",
                "RN": "%:R#%",
                "CBID": "%:wGROUP%",
                "FP": "%:UNCPG_PATHONLY%",
                "CRTD": "%:wCREATED%",
                "ACC": "%:wACCESSED%",
                "CHKOUT_TO_PREF": "%:CHKOUT_TO_PREF%",
                "CHKOUT_TO_NAME": "%:CHKOUT_TO_NAME%",
                "CHKOUT_ON_PREF": "%:CHKOUT_ON_PREF%",
                "CHKOUT_ON_DATE": "%:CHKOUT_ON_DATE%",
                "CHKOUT_TO_LINE": "%:CHKOUT_TO_LINE%",
                "FPR": "%:UNCPG_PATHFILE%",
                "PSL": "%SHARED_LINK%",
                "PSU": "%SHARED_USER%",
                "PSD": "%SHARED_DATE%"
            }
        ]
    }
}
  ```
