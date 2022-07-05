---
layout: default
title: Worldox Web 3.x API Overview
nav_order: 3
---

AEDTABLE (Add, Edit and Delete Table)
=====================================

Add, edit or delete tables.

[AEDTABLE Parameters](#aedtable-parameters)

[AEDTABLE Usage](#aedtable-usage)

[AEDTABLE Possible Erors](#aedtable-possible-errors)

[JSON Successful AEDTABLE Response](#json-successful-aedtable-response)

[JSON Failed AEDTABLE Response](#json-failed-aedtable-response)

## AEDTABLE Parameters

```
wd_FILE_PROFILEGROUP_VALUE = Number: Cabinet#
wd_FIELD_NUMBER_VALUE = Number: 1-7
wd_FILE_FIELD1_VALUE = String: Table field code
wd_FILE_FIELD2_VALUE = String: Table field code
wd_FILE_FIELD3_VALUE = String: Table field code
wd_FILE_FIELD4_VALUE = String: Table field code
wd_FILE_FIELD5_VALUE = String: Table field code
wd_FILE_FIELD6_VALUE = String: Table field code
wd_FILE_FIELD7_VALUE = String: Table field code
wd_FILE_FIELD1DESC_VALUE = String: Table field description
wd_FILE_FIELD2DESC_VALUE = String: Table field description
wd_FILE_FIELD3DESC_VALUE = String: Table field description
wd_FILE_FIELD4DESC_VALUE = String: Table field description
wd_FILE_FIELD5DESC_VALUE = String: Table field description
wd_FILE_FIELD6DESC_VALUE = String: Table field description
wd_FILE_FIELD7DESC_VALUE = String: Table field description
```

## AEDTABLE Usage

`wd_FIELD_NUMBER_VALUE` determines what table is being set.

Set the `wd_FILE_FIELDx_VALUE` for the target field being added/edited/deleted.

Set the `wd_FILE_FIELDxDESC_VALUE` as desired. If set to “/DELETE”, the field is deleted.

If the field has parent(s), set the parent codes accordingly. (Otherwise, you do not need to define them.)

Global codes are created if no parent is defined.

## AEDTABLE Possible errors
```
WDRC_AEDTABLE_PARENT_INVALID
WDRC_AEDTABLE_CODE_INVALID
WDRC_AEDTABLE_CODE_TOOLONG
WDRC_AEDTABLE_CODE_ILLEGAL
WDRC_AEDTABLE_CODE_RESTRICTED
WDRC_AEDTABLE_CODE_REQUIRED
WDRC_AEDTABLE_DESC_REQUIRED
WDRC_AEDTABLE_NUMBER_INVALID
WDRC_AEDTABLE_NUMBER_REQUIRED
WDRC_AEDTABLE_FAIL_OPEN
WDRC_AEDTABLE_FAIL_ADD
WDRC_AEDTABLE_FAIL_EDIT
WDRC_AEDTABLE_FAIL_DELETE

```

## JSON Successful AEDTABLE Response
Note that when the response is successful, the `ErrorCount` value is blank. 

```
{
    "root": {
        "data": {
            "XN": "",
            "LN": "",
            "RN": "",
            "FN": "",
            "C": "",
            "PF": "",
            "V": "",
            "O": "",
            "1C": "50000",
            "1D": "Casin, William F.",
            "2C": "600",
            "2D": "natalie's test matter 6s",
            "3C": "",
            "3D": "",
            "4C": "",
            "4D": "",
            "5C": "",
            "5D": "",
            "6C": "",
            "6D": "",
            "7C": "",
            "7D": "",
            "ID": "",
            "S": "",
            "I": "",
            "AT": "",
            "CT": "",
            "UT": "",
            "PM": "",
            "DN": "",
            "CHKOUT_TO_NAME": "",
            "List_ID": ""
        },
        "errorStatus": {
            "ErrorCount": "",
            "wd_Error_RCID": "8740",
            "wd_Error_RCTX": "WDRC_SID_INVALID",
            "wd_Error_MSG": "WDRC_SID_INVALID",
            "wd_Error_VAR": "wd_SID",
            "wd_Error_VAL": "null",
            "wd_Error_DOCID": "",
            "wd_Error_DOCNAME": "",
            "req_ID": "",
            "Error": [
                {
                    "wd_Error_RCID": "8740",
                    "wd_Error_RCTX": "WDRC_SID_INVALID",
                    "wd_Error_MSG": "WDRC_SID_INVALID",
                    "wd_Error_VAR": "wd_SID",
                    "wd_Error_VAL": "null"
                }
            ]
        }
    }
}
```

## JSON Failed AEDTABLE Response
Note that when the response has failed, the `ErrorCount` value has a number, the `RCTX` value determines what the error is. The Worldox API always returns a `200` status even on failure.  

```
{
    "root": {
        "data": {
            "XN": "",
            "LN": "",
            "RN": "",
            "FN": "",
            "C": "",
            "PF": "",
            "V": "",
            "O": "",
            "1C": "50000",
            "1D": "Casin, William F.",
            "2C": "600",
            "2D": "natalie's test matter 6s",
            "3C": "",
            "3D": "",
            "4C": "",
            "4D": "",
            "5C": "",
            "5D": "",
            "6C": "",
            "6D": "",
            "7C": "",
            "7D": "",
            "ID": "",
            "S": "",
            "I": "",
            "AT": "",
            "CT": "",
            "UT": "",
            "PM": "",
            "DN": "",
            "CHKOUT_TO_NAME": "",
            "List_ID": ""
        },
        "errorStatus": {
            "ErrorCount": "1",
            "wd_Error_RCID": "8740",
            "wd_Error_RCTX": "WDRC_SID_INVALID",
            "wd_Error_MSG": "WDRC_SID_INVALID",
            "wd_Error_VAR": "wd_SID",
            "wd_Error_VAL": "Xkx8QpA9DyxLzFLVB0fbhm$2FmbfUDSGF8skLTZfmOJLxV74onmUF048D$2Bkjk$3Ddonna",
            "wd_Error_DOCID": "",
            "wd_Error_DOCNAME": "",
            "req_ID": "",
            "Error": [
                {
                    "wd_Error_RCID": "8740",
                    "wd_Error_RCTX": "WDRC_SID_INVALID",
                    "wd_Error_MSG": "WDRC_SID_INVALID",
                    "wd_Error_VAR": "wd_SID",
                    "wd_Error_VAL": "Xkx8QpA9DyxLzFLVB0fbhm$2FmbfUDSGF8skLTZfmOJLxV74onmUF048D$2Bkjk$3Ddonna"
                }
            ]
        }
    }
}
```
