---
layout: default
title: TESTPROFILE
nav_order: 22
---

TESTPROFILE
The TESTPROFILE command tests the file’s profile information to ensure that no fields are missing or invalid. This is a GET request.
25.1	TESTPROFILE Example
{Worldox Web Domain}  + 'cgi-bin/wdwebcgi.exe?TESTPROFILE+wd_SID=' + {Worldox Web User Session) + '+wd_File_Field1_Value=' + y.field1.value + '+wd_File_Field2_Value=' + y.field2.value + '+wd_File_Field3_Value=' + y.field3.value + '+wd_File_Field4_Value=' + y.field4.value + '+wd_File_Field5_Value=' + y.field5.value + '+wd_File_Field6_Value=' + y.field6.value + '+wd_File_Field7_Value=' + y.field7.value + '+wd_File_ProfileGroup_Value=' + pgID + '+HTMLOnOK=/v4/testprofile/test-profile.json+HTMLOnFail=/v4/testprofile/test-profile.json+wd_File_Path_Filter=PATH'
25.2	Parameters
HTMLOnOK
This is the page to return on a successful call to TESTPROFILE.
v4 \testprofile\test-profile.json
Note: api is deprecated but still can be used. Going forward v4 is the best practice.
HTMLOnFail
This is the page to return on a failed TESTPROFILE.
v4 \testprofile\test-profile.json
Note: api is deprecated but still can be used. Going forward v4 is the best practice.
{Worldox Web Domain} 
	Is the domain name
wd_SID
	Is the session ID
{Worldox Web User Session)
	Is the variable
wd_File_Field1_Value
File’s field 1 value.
wd_File_Field2_Value
File’s field 2 value.
wd_File_Field3_Value
File’s field 3 value
wd_File_Field4_Value
File’s field 4 value
wd_File_Field5_Value
File’s field 5 value
wd_File_Field6_Value
File’s field 6 value
wd_File_Field7_Value
File’s field 7 value
wd_File_ProfileGroup_Value(5350)
	This is the file’s cabinet (profile group) value.
wd_File_Path_Filter
	This is the file path’s filter. It can pass an empty parameter.
PATH
		accesses a path and folder-level fields
SAVE
creates or uploads a file
Note: If wd_File_Path_Filter parameter is empty, it defaults to SAVE.
25.3	JSON Successful TESTPROFILE Response
Note that when the response is successful, the ErrorCount value is blank. 
{
    "root": {
        "errorStatus": {
            "List_Count": "",
            "ErrorCount": "",
            "Error": ""
        },
        "data": {
            "Fields": {
                "Field1": {
                    "wd_File_Field_Value": "00001",
                    "wd_File_Field_Desc": "00001",
                    "wd_File_Field_Error": "",
                    "wdField": "1"
                },
                "Field2": {
                    "wd_File_Field_Value": "0010",
                    "wd_File_Field_Desc": "General",
                    "wd_File_Field_Error": "",
                    "wdField": "2"
                },
                "Field3": {
                    "wd_File_Field_Value": "",
                    "wd_File_Field_Desc": "",
                    "wd_File_Field_Error": "",
                    "wdField": "3"
                },
                "Field4": {
                    "wd_File_Field_Value": "",
                    "wd_File_Field_Desc": "",
                    "wd_File_Field_Error": "",
                    "wdField": "4"
                },
                "Field5": {
                    "wd_File_Field_Value": "",
                    "wd_File_Field_Desc": "",
                    "wd_File_Field_Error": "",
                    "wdField": "5"
                },
                "Field6": {
                    "wd_File_Field_Value": "",
                    "wd_File_Field_Desc": "",
                    "wd_File_Field_Error": "",
                    "wdField": "6"
                },
                "Field7": {
                    "wd_File_Field_Value": "",
                    "wd_File_Field_Desc": "",
                    "wd_File_Field_Error": "",
                    "wdField": "7"
                }
            },
            "session": "EHgRICvIKW4FNzZGxI$2Fxw6XR7Ag0Y5zbpsntEjhfiLLdCTZkz$2BaFbdWCx$2F4$3D",
            "wdPath": "%5C%5Cfs01%5Cworldox%5Cdata%5CWDOX%5CClients%5C00001%5C0010",
            "wd_File_ProfileGroup_Value": "5"
        }
    }
}
25.4	JSON Failed TESTPROFILE Response
Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  
{
    "root": {
        "errorStatus": {
            "List_Count": "",
            "ErrorCount": "1",
            "Error": [
                {
                    "wd_Error_RCID": "8120",
                    "wd_Error_RCTX": "WDRC_CABINET_INVALID",
                    "wd_Error_VAR": "",
                    "wd_Error_VAL": ""
                }
            ]
        },
        "data": {
            "Fields": {
                "Field1": {
                    "wd_File_Field_Value": "",
                    "wd_File_Field_Desc": "",
                    "wd_File_Field_Error": "",
                    "wdField": "1"
                },
                "Field2": {
                    "wd_File_Field_Value": "",
                    "wd_File_Field_Desc": "",
                    "wd_File_Field_Error": "",
                    "wdField": "2"
                },
                "Field3": {
                    "wd_File_Field_Value": "",
                    "wd_File_Field_Desc": "",
                    "wd_File_Field_Error": "",
                    "wdField": "3"
                },
                "Field4": {
                    "wd_File_Field_Value": "",
                    "wd_File_Field_Desc": "",
                    "wd_File_Field_Error": "",
                    "wdField": "4"
                },
                "Field5": {
                    "wd_File_Field_Value": "",
                    "wd_File_Field_Desc": "",
                    "wd_File_Field_Error": "",
                    "wdField": "5"
                },
                "Field6": {
                    "wd_File_Field_Value": "",
                    "wd_File_Field_Desc": "",
                    "wd_File_Field_Error": "",
                    "wdField": "6"
                },
                "Field7": {
                    "wd_File_Field_Value": "",
                    "wd_File_Field_Desc": "",
                    "wd_File_Field_Error": "",
                    "wdField": "7"
                }
            },
            "session": "5tlzyRw9ghLzT8tFINjDb6A0tzywhSs88YETpzzTbAejQeGDe$2BkDWU5nItI$3D",
            "wdPath": "",
            "wd_File_ProfileGroup_Value": ""
        }
    }
}
 
