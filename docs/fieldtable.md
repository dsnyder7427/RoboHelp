# FIELDTABLE
The FIELDTABLE command obtains the field table based on pre-filled metadata.

[FIELDTABLE Example](#fieldtable-example)

[FIELDTABLE Parameters](#fieldtable-parameters)

[JSON Successful FIELDTABLE Response for a Linked Field table](#json-successful-fieldtable-response-for-a-linked-field-table)

[JSON Successful FIELDTABLE Response for a Non-Linked Field table](#json-successful-fieldtable-response-for-a-non-linked-field-table)

[JSON Failed FIELDTABLE Response](#json-failed-fieldtable-response)

## FIELDTABLE Example
```
{Worldox Web Domain}/cgi-bin/wdwebcgi.exe?FIELDTABLE+wd_SID={Worldox Web User Session}+HTMLOnOk=/v4/fieldtables/fieldTables.json+HTMLOnFail=/v4/fieldtables/fieldTables.json+wd_FIELD_PROFILEGROUP_FILTER={Cabinet ID}+wd_FIELD1CODE_FILTER={Field 1 Value}+wd_FIELD2CODE_FILTER={Field 2 Value}+wd_FIELD3CODE_FILTER={Field 3 Value}+wd_FIELD4CODE_FILTER={Field 4 Value}+wd_FIELD5CODE_FILTER={Field 5 Value}+wd_FIELD6CODE_FILTER={Field 6 Value}+wd_FIELD7CODE_FILTER={Field 7 Value}+wd_FIELD_NUMBER_FILTER={Field for the table you want to obtain}+maxCount={Total amount of Field tables shown}+IndexFr={Index where to start the Field table list}+wd_List_Filter={inserted text that filters current list}
```

## FIELDTABLE Parameters
`{Worldox Web Domain}`

Is the domain name

`wd_SID`

	Is the session ID

`HTMLOnOK`

This is the page to return on a successful call to FIELDTABLE.

`v4 \fieldtables\fieldTables.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`HTMLOnFail`

This is the page to return on a failed FIELDTABLE.

`v4 \fieldtables\fieldTables.json`

**Note:** `api`is deprecated but still can be used. Going forward v4 is the best practice.

`wd_FIELD_PROFILEGROUP_FILTER`
	Is the Cabinet ID

`wd_FIELD1CODE_FILTER`
	Field 1 value

`wd_FIELD2CODE_FILTER`
	Field 2 value

`wd_FIELD3CODE_FILTER`
	Field 3 value

`wd_FIELD4CODE_FILTER`
	Field 4 value

`wd_FIELD5CODE_FILTER`
	Field 5 value

`wd_FIELD6CODE_FILTER`
	Field 6 value

`w_FIELD7CODE_FILTER`
	Field 7 value

`wd_List_Flags=0`
	List ID flag (indicates if the file list has flags). This value is empty for Active field tables, the default.
	`2304`returns Inactive field tables.
	`3328` returns All (Active and Inactive) field tables.

`wd_FIELD_ACTIVE_VALUE`
	ACTIVE can be `1` or `0`.
	`1` is used for an Active field table
	`0` is used for an Inactive field table

`wd_FIELD_RETMETHOD_VALUE` 
Retention method values are:
		`A` Archive
		`D` Delete
		`N` No Action (will be blank in code)

`wd_FIELD_RETSCALE_VALUE`
	Retention Scale values are:
	`W` Week
	`M` Month
	`Y` Year

`wd_FIELD_RETUNITS_VALUE`
	Retention units are numeric values

`MaxCount`
	Maximum number of records to return. Uses Skip and Take for field tables. Skip Is where you start. 0 is the value. Take Is set to 500, which is the current default. **Note:** In the future, you can configure this to be a greater value. 
`IndexFr`
	Index where to start the field table

`wd_List_Filter`
	Is not a required parameter, but when it is used, it will filter by field code and field description.
	The value for wd_List_Filter can be surrounded by an * asterisk.
	If the value is `*`001, it will return all field tables that start with 001 on the field that is selected in the wd_FIELD_NUMBER_FILTER
	If the value is 001* , it will return all field tables that end with 001 on the field that is selected in the wd_FIELD_NUMBER_FILTER
	If the value is *001*, it will return all field tables that contains 001 on the field that is selected in the wd_FIELD_NUMBER_FILTER

## FIELDTABLE Sort Directions
```
wd_File_Field1_Value(5320)
wd_File_Field2_Value(5324)
wd_File_Field3_Value(5328)
wd_File_Field4_Value(5332)
wd_File_Field5_Value(5336)
wd_File_Field6_Value(5340)
wd_File_Field7_Value(5344)
wd_File_Field1Desc_Value(5322)
wd_File_Field2Desc_Value(5326)
wd_File_Field3Desc_Value(5330)
wd_File_Field4Desc_Value(5334)
wd_File_Field5Desc_Value(5338)
wd_File_Field6Desc_Value(5342)
wd_File_Field7Desc_Value(5346)
```

## JSON Successful FIELDTABLE Response for a non-Linked Field Table 

Note that when the response is successful, the ErrorCount value is blank. 

```
{
    "root": {
        "errorStatus": {
            "List_Count": 1,
            "List_ID": "x1B59BA8",
            "ErrorCount": "",
            "wd_Error_RCID": "",
            "wd_Error_RCTX": "",
            "wd_Error_MSG": "",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "FieldNum": "1",
            "Error": ""
        },
        "data": [
            {
                "f1n": "916",
                "f1d": "EP-LF EP-LF",
                "HASH": "x94D64C1B",
                "ln": 1
            }
        ]
    }
}
```

## JSON Successful FIELDTABLE Response for a Linked Field Table

Note that when the response is successful, the ErrorCount value is blank. 
The following is successful code output shown for FIELDTABLES where fields are linked (for example, Client and Matter). 

```
{
    "root": {
        "errorStatus": {
            "List_Count": 1359,
            "List_ID": "x26BC398",
            "ErrorCount": "",
            "wd_Error_RCID": "",
            "wd_Error_RCTX": "",
            "wd_Error_MSG": "",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "FieldNum": "1",
            "Error": ""
        },
        "data": [
            {
                "f1n": "00001",
                "f1d": "00001",
                "HASH": "xC2F96AC1",
                "ln": 1
            },
            {
                "f1n": "00002",
                "f1d": "00002",
                "HASH": "xD925CC01",
                "ln": 2
            }
        ]
    }
}
```
## JSON Failed FIELDTABLE Response

Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  

```
{
    "error": 404,
    "message": "File doesn't exist",
    "wd_Error_Count": 1,
    "wd_Error_MSG": "C:\\WorldoxWeb3\\JSON\\20201120\\v4\\fieldtables\\fieldTables.jso",
    "wd_Error_RCID": 8275,
    "wd_Error_RCTX": "WDRC_FILE_NOT_FOUND"
}
```
