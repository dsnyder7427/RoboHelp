---
layout: default
title: RENAME
nav_order: 19
---

# RENAME (EDIT META DATA) 

The RENAME command copies, moves, edits, deletes, and creates new versions of the Worldox profile. This also applies to Salvage, Archive and Legal Hold features in Worldox.

[RENAME Example](#rename-example)

[RENAME Parameters](#rename-parameters)

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




