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

**JSON Key**

**Slim Parameter**

**Meaning**

“Description”

"%Xname%",

File description

"DocId"

"%DOCID%", 

File name

"DateUpdated",

"%wUPDATED%",

unixtimestamp of date updated

"Size",

"%SIZE%",

File size

"Comments",

"%COMMENTS%",

File comments

"Version",

"%VERSION%",

Version number

"I",

"%wSTATUSID%",

Numerical value of file status (checked-out etc.)

"dwRC",

"%dwRC%",

Return code of the file (if it is missing from the file system)

"stFl",

"%wSTATUS\_FLAGS%",

Status flags #

"stIc",

"%wSTATUS\_ICON%",

Status icon #

"HASH",

"%H#%",

Hash of every value above it

"FilePath",

"%UNCPG\_PATHONLY%",

Descriptive path of file

"FilePathReal",

"%UNCPG\_PATHFILE%",

Physical path of file

"LN",

"%L#%",

File offset

"RN",

"%R#%",

File record number

"LID",

"^wd\_List\_ID^",

List ID of current list

"Field1",

"%FIELD1%",

Field 1 code

"Field1Desc",

"%FIELD1DESC%",

Field 1 description

"Field1Name",

"%Field1Name%",

Field 1 name

"Field2",

"%FIELD2%",

Field 2 code

"Field2Desc",

"%FIELD2DESC%",

Field 2 description

"Field2Name",

"%Field2Name%",

Field 2 name

"Field3",

"%FIELD3%",

Field 3 code

"Field3Desc",

"%FIELD3DESC%",

Field 3 description

"Field3Name",

"%Field3Name%",

Field 3 name

"Field4",

"%FIELD4%",

Field 4 code

"Field4Desc",

"%FIELD4DESC%",

Field 4 description

"Field4Name",

"%Field4Name%",

Field 4 name

"Field5",

"%FIELD5%",

Field 5 code

"Field5Desc",

"%FIELD5DESC%",

Field 5 description

"Field5Name",

"%Field5Name%",

Field 5 name

"Field6",

"%FIELD6%",

Field 6 code

"Field6Desc",

"%FIELD6DESC%",

Field 6 description

"Field6Name",

"%Field6Name%",

Field 6 name

"Field7",

"%FIELD7%",

Field 7 code

"Field7Desc",

"%FIELD7DESC%",

Field 7 description

"Field7Name",

"%Field67Name%",

Field 7 name

"AccessedDate",

"%wACCESSED%",

unix timestamp of date accessed

"DateCreated",

"%wCREATED%",

unix timestamp of date created

"PathMap",

"%PATHMAP%",

“Hidden” path of file

"ProfileGroupId",

"%wGROUP%",

Cabinet ID

"Cabinet",

"%GROUP%",

Cabinet name

"Location",

"%PATH%",

Descriptive path

"Extension",

"%EXT%",

File extension

"OW",

"%OWNERINIT%",

Owner initials (last person to access the file

"FF",

"%FAVORITE%",

Is this file a favorite? If so, how?

"EFR",

"%EMAIL\_FR%",

Email was from

"ETO",

"%EMAIL\_TO%",

Email was to

"ECC",

"%EMAIL\_CC%",

Email had CC

"EBC",

"%EMAIL\_BCC%",

Email had bcc

"ETS",

"%EMAIL\_tSENT%",

Time email was sent

"ETR",

"%EMAIL\_tRCVD%",

Time email was received

"ERF",

"%EMAIL\_tRFDATE%",

Received from date

"ERW",

"%EMAIL\_RFWHO%",

Received from person

"EAD",

"%EMAIL\_ADDR%",

Email from

"szRC",

"%szRC%",

dwRCs error text

"CHKOUT\_TO\_PREF",

"%CHKOUT\_TO\_PREF%",

Part of the checked-out line

"CHKOUT\_TO\_NAME",

"%CHKOUT\_TO\_NAME%",

Part of the checked-out line

"CHKOUT\_ON\_PREF",

"%CHKOUT\_ON\_PREF%",

Part of the checked-out line

"CHKOUT\_ON\_DATE",

"%CHKOUT\_ON\_DATE%",

Part of the checked-out line

"CHKOUT\_TO\_LINE",

"%CHKOUT\_TO\_LINE%",

Full checked out-line

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
