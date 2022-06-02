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

```
wd\_FILE\_PROFILEGROUP\_VALUE = Number: Cabinet#

wd\_FIELD\_NUMBER\_VALUE = Number: 1-7

wd\_FILE\_FIELD1\_VALUE = String: Table field code  
wd\_FILE\_FIELD2\_VALUE = String: Table field code  
wd\_FILE\_FIELD3\_VALUE = String: Table field code  
wd\_FILE\_FIELD4\_VALUE = String: Table field code  
wd\_FILE\_FIELD5\_VALUE = String: Table field code  
wd\_FILE\_FIELD6\_VALUE = String: Table field code  
wd\_FILE\_FIELD7\_VALUE = String: Table field code

wd\_FILE\_FIELD1DESC\_VALUE = String: Table field description  
wd\_FILE\_FIELD2DESC\_VALUE = String: Table field description  
wd\_FILE\_FIELD3DESC\_VALUE = String: Table field description  
wd\_FILE\_FIELD4DESC\_VALUE = String: Table field description  
wd\_FILE\_FIELD5DESC\_VALUE = String: Table field description  
wd\_FILE\_FIELD6DESC\_VALUE = String: Table field description  
wd\_FILE\_FIELD7DESC\_VALUE = String: Table field description
```

## AEDTABLE Usage

wd\_FIELD\_NUMBER\_VALUE determines what table is being set.

Set the wd\_FILE\_FIELDx\_VALUE for the target field being added/edited/deleted.

Set the wd\_FILE\_FIELDxDESC\_VALUE as desired. If set to “/DELETE”, the field is deleted.

If the field has parent(s), set the parent codes accordingly. (Otherwise, you do not need to define them.)

Global codes are created if no parent is defined.

## AEDTABLE Possible errors
```
WDRC\_AEDTABLE\_PARENT\_INVALID  
WDRC\_AEDTABLE\_CODE\_INVALID  
WDRC\_AEDTABLE\_CODE\_TOOLONG  
WDRC\_AEDTABLE\_CODE\_ILLEGAL  
WDRC\_AEDTABLE\_CODE\_RESTRICTED  
WDRC\_AEDTABLE\_CODE\_REQUIRED  
WDRC\_AEDTABLE\_DESC\_REQUIRED  
WDRC\_AEDTABLE\_NUMBER\_INVALID  
WDRC\_AEDTABLE\_NUMBER\_REQUIRED  
WDRC\_AEDTABLE\_FAIL\_OPEN  
WDRC\_AEDTABLE\_FAIL\_ADD  
WDRC\_AEDTABLE\_FAIL\_EDIT  
WDRC\_AEDTABLE\_FAIL\_DELETE
```

## JSON Successful AEDTABLE Response

```
{

    "root": {

        "data": {

            "XN": "",

            "LN": "",

            "RN": "",

            "FN": "",

            "C": "",

            "PF": "",

            "V": "",

            "O": "",

            "1C": "50000",

            "1D": "Casin, William F.",

            "2C": "600",

            "2D": "natalie's test matter 6s",

            "3C": "",

            "3D": "",

            "4C": "",

            "4D": "",

            "5C": "",

            "5D": "",

            "6C": "",

            "6D": "",

            "7C": "",

            "7D": "",

            "ID": "",

            "S": "",

            "I": "",

            "AT": "",

            "CT": "",

            "UT": "",

            "PM": "",

            "DN": "",

            "CHKOUT\_TO\_NAME": "",

            "List\_ID": ""

        },

        "errorStatus": {

            "ErrorCount": "",

            "wd\_Error\_RCID": "8740",

            "wd\_Error\_RCTX": "WDRC\_SID\_INVALID",

            "wd\_Error\_MSG": "WDRC\_SID\_INVALID",

            "wd\_Error\_VAR": "wd\_SID",

            "wd\_Error\_VAL": "null",

            "wd\_Error\_DOCID": "",

            "wd\_Error\_DOCNAME": "",

            "req\_ID": "",

            "Error": \[

                {

                    "wd\_Error\_RCID": "8740",

                    "wd\_Error\_RCTX": "WDRC\_SID\_INVALID",

                    "wd\_Error\_MSG": "WDRC\_SID\_INVALID",

                    "wd\_Error\_VAR": "wd\_SID",

                    "wd\_Error\_VAL": "null"

                }

            \]

        }

    }

}
```
## JSON Failed AEDTABLE Response

```
{

    "root": {

        "data": {

            "XN": "",

            "LN": "",

            "RN": "",

            "FN": "",

            "C": "",

            "PF": "",

            "V": "",

            "O": "",

            "1C": "50000",

            "1D": "Casin, William F.",

            "2C": "600",

            "2D": "natalie's test matter 6s",

            "3C": "",

            "3D": "",

            "4C": "",

            "4D": "",

            "5C": "",

            "5D": "",

            "6C": "",

            "6D": "",

            "7C": "",

            "7D": "",

            "ID": "",

            "S": "",

            "I": "",

            "AT": "",

            "CT": "",

            "UT": "",

            "PM": "",

            "DN": "",

            "CHKOUT\_TO\_NAME": "",

            "List\_ID": ""

        },

        "errorStatus": {

            "ErrorCount": "1",

            "wd\_Error\_RCID": "8740",

            "wd\_Error\_RCTX": "WDRC\_SID\_INVALID",

            "wd\_Error\_MSG": "WDRC\_SID\_INVALID",

            "wd\_Error\_VAR": "wd\_SID",

            "wd\_Error\_VAL": "Xkx8QpA9DyxLzFLVB0fbhm$2FmbfUDSGF8skLTZfmOJLxV74onmUF048D$2Bkjk$3Ddonna",

            "wd\_Error\_DOCID": "",

            "wd\_Error\_DOCNAME": "",

            "req\_ID": "",

            "Error": \[

                {

                    "wd\_Error\_RCID": "8740",

                    "wd\_Error\_RCTX": "WDRC\_SID\_INVALID",

                    "wd\_Error\_MSG": "WDRC\_SID\_INVALID",

                    "wd\_Error\_VAR": "wd\_SID",

                    "wd\_Error\_VAL": "Xkx8QpA9DyxLzFLVB0fbhm$2FmbfUDSGF8skLTZfmOJLxV74onmUF048D$2Bkjk$3Ddonna"

                }

            \]

        }

    }

}
```
