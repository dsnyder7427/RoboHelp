---
layout: default
title: SORTFILES
nav_order: 21
---

[
# SORTFILES

The SORTFILES command can be called to re-sort a list. Note: FINDFILES is used for GetList and Create Temp list. SORTFILES is a separate command, but it can use the same output as FINDFILES.

[SORTFILES Example](#sortfiles-example)

[SORTFILES Parameters](#sorftiles-parameters)

[Sort Values](#sort-values)

[JSON Successful SORTFILES Response](#json-successful-sortfiles-response)

[JSON Failed SORTFILES Response](#json-failed-sortfiles-response)


## SORTFILES Example

`{{domain}}/cgi-bin/wdwebcgi.exe?SORTFILES&wd_SID={{session}}&wd_List_ID={{File list ID}}&Wd_File_Sort_Key1={{columnID}}&wd_File_Sort_Dir1={{ 0 for accending / 1 for decending }}&skip={{ numeric digit where to start the list }}&take={{ numeric digit where to stop the list }}&html=/v4/filelist/fileList.json`

## SORTFILES Parameters

`wd_SID`

This command is the Worldox session ID.

`HTMLOnOK`

This is the page to return on a successful call to SORTFILES.

`v4\fileList\fileList.json` 

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`HTMLOnFail`

This is the page to return on a failed upload.

`v4\fileList\fileList.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`Skip`

Is where you start. 0 is the value. 

`Take`

Is set to 500, which is the current default. Note: In the future, you can configure this to be a greater value. 

`wd_List_ID(6254)`

Parameter previously returned from FINDFILES.

`Wd_List_RecNum(6262)`

Set to 0

`Wd_File_Sort_Key1(6282)`

Primary Sort key

`Wd_File_Sort_Key2(6284)`

Secondary Sort key

`Wd_File_Sort_Key1(6290)`

Primary Sort Direction

`Wd_File_Sort_Key2(6292)`

Secondary Sort Direction

`Offset`

(Starting offset) set to 1

## Sort Values

`wd_File_Updated_Value`

5374

`wd_File_Version_Value`

5376

`wd_File_Size_Value`

5368

`wd_File_Xname_Value`

5380

`wd_File_FileName_Value`

5348

## JSON Successful SORTFILES Response

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

## JSON Failed SORTFILES Response

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
            "wd_Error_VAL": "J7KPzFjkE0EyoELa8eXqasFxELHbNVwX8p5M$2FK1gFcyFP$2Fu5JR6OhgNAHuo$3D4wa0hi0psi[h",
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
                    "wd_Error_VAL": "J7KPzFjkE0EyoELa8eXqasFxELHbNVwX8p5M$2FK1gFcyFP$2Fu5JR6OhgNAHuo$3D4wa0hi0psi[h"
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
                "LID": "",
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
                "AFP": "%:uncpg%",
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
 

