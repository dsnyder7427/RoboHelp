---
layout: default
title: NEWFILE
nav_order: 16
---

# NEWFILE

The NEWFILE command saves the uploaded file into Worldox. 

[NEWFILE Example](#newfile-example)

[NEWFILE Parameters](#newfile-parameters)

[JSON Successful NEWFILE Response](#json-successful-newfile-response)

[JSON Failed NEWFILE Response](#json-failed-newfile-response)


## NEWFILE Example

`{{url}}/cgi-bin/wdwebcgi.exe?NEWFILE&wd_SID={{session}}&HtmlOnOK=/v4/fileActions/Newfile.json&HtmlOnFail=/v4/fileActions/Newfile.json&Wd_File_Field1_Value={{wdField1}}&Wd_File_Field2_Value={{wdField2}}&Wd_File_Field3_Value={{wdField3}}&Wd_File_Field4_Value={{wdField4}}&Wd_File_Field5_Value={{wdField5}}&Wd_File_Field6_Value={{wdField6}}&Wd_File_Field7_Value={{wdField7}}&Wd_File_ProfileGroup_Value={{wdPgroup}}&Wd_File_Xname_Value={{wdXname}}&Wd_File_StatusFlags_Value={{wdStatusFlag}}&wd_FILE_FILENAME_VALUE={{wdFileName}}&fileExt=.pdf`

## NEWFILE Parameters

 `HTMLOnOK`

  	This is the page to return on a successful call to NEWFILE.

  `v4 \fileActions\Newfile.json` 

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`HTMLOnFail`

  This is the page to return on a failed NEWFILE.

  `v4 \fileActions\Newfile.json` 

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`{Worldox Web Domain}` 
	
  Is the domain name

`wd_SID`

	Is the session ID

`wd_File_Field1_Value`

	File’s field 1 value

`wd_File_Field2_Value`

	File’s field 2 value

`wd_File_Field3_Value`

	File’s field 3 value

`wd_File_Field4_Value`

	File’s field 4 value

`wd_File_Field5_Value`

	File’s field 5 value

`wd_File_Field6_Value`

	File’s field 6 value

`wd_File_Field7_Value`

	File’s field 7 value

`wd_File_ProfileGroup_Value`

	File’s cabinet (profile group) value

`wd_File_XNAME_Value`

	This is the description

`wd_FILE_STATUSFLAGS_VALUE`

	Security ID flag (indicates if the file has security and if so, what type- none, protected or hidden)

`wd_file_filename_value`

	Is my_filename_description.docx (This is an example)

`fileExt`

	Is the file’s extension (for example, .docx, .xlsx, .pdf, etc.)

## JSON Successful NEWFILE Response

Note that when the response is successful, the ErrorCount value is blank. 

```
{
    "root": {
        "data": {
            "Cabinet": "5",
            "Description": "",
            "Security": "",
            "Extension": "",
            "FileField1": "00001",
            "FileField2": "0010",
            "FileField3": "AGD",
            "FileField4": "",
            "FileField5": "QC4",
            "FileField6": "QC4",
            "FileField7": "",
            "FileField1Desc": "00001",
            "FileField2Desc": "General",
            "FileField3Desc": "Agenda",
            "FileField4Desc": "",
            "FileField5Desc": "QC User4",
            "FileField6Desc": "QC User4",
            "FileField7Desc": "",
            "wd_File_Field_Error1": "",
            "wd_File_Field_Error2": "",
            "wd_File_Field_Error3": "",
            "wd_File_Field_Error4": "",
            "wd_File_Field_Error5": "",
            "wd_File_Field_Error6": "",
            "wd_File_Field_Error7": "",
            "UploadTo": "/cgi-bin/WDSIDS/2zb7uLuyBl7OwNfQTjKih$2FPp8$2F$2F2pC0gVWuDnbjV9BU3W4GpjthaHQGp7iM$3D/SAVE",
            "FileZMS": "\\WORLDOX\\ZMS\\005\\00001\\0010\\00016628.docx",
            "FileLID": "x26BC660",
            "FileRN": "3",
            "Name": "Qc4 test upload from postman again (00016628x51615).DOCX",
            "DocId": "00016628.docx",
            "Path": "\\\\fs01\\worldox\\data\\WDOX\\Clients\\00001\\0010"
        },
        "errorStatus": {
            "List_Count": "",
            "ErrorCount": "",
            "Error": []
        }
    }
}
```
 
## JSON Failed NEWFILE Response

Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  

```
{
    "root": {
        "data": {
            "Cabinet": "",
            "Description": "",
            "Security": "",
            "Extension": "",
            "FileField1": "",
            "FileField2": "",
            "FileField3": "",
            "FileField4": "",
            "FileField5": "",
            "FileField6": "",
            "FileField7": "",
            "FileField1Desc": "",
            "FileField2Desc": "",
            "FileField3Desc": "",
            "FileField4Desc": "",
            "FileField5Desc": "",
            "FileField6Desc": "",
            "FileField7Desc": "",
            "wd_File_Field_Error1": "",
            "wd_File_Field_Error2": "",
            "wd_File_Field_Error3": "",
            "wd_File_Field_Error4": "",
            "wd_File_Field_Error5": "",
            "wd_File_Field_Error6": "",
            "wd_File_Field_Error7": "",
            "UploadTo": "",
            "FileZMS": "",
            "FileLID": "",
            "FileRN": "",
            "Name": "",
            "DocId": "archive-blah2.txt",
            "Path": ""
        },
        "errorStatus": {
            "List_Count": "",
            "ErrorCount": "1",
            "Error": [
                {
                    "wd_Error_RCID": "8740",
                    "wd_Error_RCTX": "WDRC_SID_INVALID",
                    "wd_Error_MSG": "WDRC_SID_INVALID",
                    "wd_Error_VAR": "wd_SID"
                }
            ]
        }
    }
}
```
