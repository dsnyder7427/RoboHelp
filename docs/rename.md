---
layout: default
title: RENAME
nav_order: 19
---

# RENAME (EDIT META DATA) 

The RENAME command copies, moves, edits, deletes, and creates new versions of the Worldox profile. This also applies to Salvage, Archive and Legal Hold features in Worldox.

[RENAME Example](#rename-example)

[RENAME Parameters](#rename-parameters)

[Available Flags for wd_List_RENAME Flags](#available-flags-for-wd-list-rename-flags)

[JSON Successful RENAME Response](#json-successful-rename-response)

[JSON Failed RENAME Response](#json-failed-rename-response)

## RENAME Example

`/cgi-bin/wdwebcgi.exe?RENAME+wd_SID={{session}}`

## RENAME Parameters

`wd_List_ID`

  List Id

 `wd_List_RecNum`

  Rec Num

`wd_List_Rename_Flags`

  What kind of rename? (Similar to `WDAPI_RF_FLAG_*`). For a list of total available flags, see Available Flags for `wd_List_Rename_Flags`.

  Optional: 
  
  `wd_File_Field#_Value`
    Fields 1-7 (assume * if undefined)
  
  `wd_FILE_STATUSFLAGS_VALUE`
    Security ID flag (indicates if the file has security and if so, what type- none, protected or hidden)
  
  `wd_File_ProfileGroup_Value`
    Cabinet ID to change to (if undefined it’s the same as the from)

`wd_File_Xname_Value`
    New description to use (ignore if undefined)
 
`wd_File_Comments_Value`

  New comments to use (ignore if undefined)

`wd_File_Category_Value`

  String of Categories to add to file. Should be (ID;ID;ID…)

`HTMLOnOK`

  This is the page to return on a successful call to RENAME.

  `v4\fileActions\Rename.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`HTMLOnFail`

  This is the page to return on a failed RENAME.

  `v4\fileActions\Rename.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.


## Available Flags for wd_List_Rename_Flags

The following table describes the available flags for `wd_List_Rename_Flags`.

| **Name** | **Value** | **Description** |
| --- | --- | --- |
| WDAPI_RF_FLAG_NONE |	0x00000000	|
| WDAPI_RF_FLAG_NEWPROFILE | 0x00000001 | (1) lpStruct = LPWDAPI_NEWPROFILE |
| WDAPI_RF_FLAG_MOVE | 0x00000008 | (8) Move File |
| WDAPI_RF_FLAG_COPY | 0x00000010 | (16) Copy File (plus versions) |
| WDAPI_RF_FLAG_COPYNOVERS | 0x00000030 | (48) Copy File (minus versions) |
| WDAPI_RF_FLAG_CREATEPATH | 0x00000040 | (64) Create target folder | 
| WDAPI_RF_FLAG_REPLACEFILE | 0x00000080 | (128) Replace existing file | 
| WDAPI_RF_FLAG_TOLONGNAME | 0x00000100 | (256) Use XNAME as Target Filename |
| WDAPI_RF_FLAG_SETFOLDERRO | 0x00000200 | (512) Set the Read-Only attribute in Target\XNAME*.* |
| WDAPI_RF_FLAG_SETFOLDERRW | 0x00000400 | (1024) Clear the Read-Only attribute in Target\XNAME*.* |
| WDAPI_RF_FLAG_NEWVERSION | 0x00000800 | (2048) Insert as new version |
| WDAPI_RF_FLAG_CLRDESTSEC | 0x00001000 | (4096) Clear Target File's Security | 
| WDAPI_RF_FLAG_ONLYNEWER | 0x00002000 | (8192) Copy/Move only NEWER files | 
| WDAPI_RF_FLAG_DELETE | 0x00004000 | (16384) Copy/Move to Salvage | 
| WDAPI_RF_FLAG_NOPROFILE | 0x00008000 | (32768) Do not copy Profile | 
| WDAPI_RF_FLAG_SHRED | 0x00010000 | (65536) Shred Source (on Delete/Move) |
| WDAPI_RF_FLAG_COPYOWNER | 0x00020000 | (131072) Copy Owner | 
| WDAPI_RF_FLAG_CHECKOUT | 0x00040000 | (262144) Check Out | 
| WDAPI_RF_FLAG_CHECKIN | 0x00080000 | (524288) Check In | 
| WDAPI_RF_FLAG_ARCHIVE | 0x00100000 | (1048576) Archive |
| WDAPI_RF_FLAG_RECORDS | 0x00200000 | (2097152) Record | 
| WDAPI_RF_FLAG_SAASOPEN | 0x00400000 | (4194304) Opened for SaaS | 
| WDAPI_RF_FLAG_ENCRYPT | 0x00800000 | (8388608) Encrypt File |

