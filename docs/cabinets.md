CABINETS
========

[CABINETS Example](#cabinets-example)

[CABINETS Parameters](#cabinets-parameters)

[JSON Successful CABINET Response](#json-successful-cabinets-response)

[JSON Failed CABINETS Response](#json-failed-cabinets-response)

## CABINETS Example

The CABINETS command retrieves a list of Cabinets.

```
/cgi-bin/wdwebcgi.exe?CABINETS&wd_SID{{session}}&html=/v4/cabinets/cabinets.json&wd_CABINET_ID_VALUE={{List of Cabinet IDs}}
```

## CABINETS Parameters

```
/api/cabinets/ cabinets.json
```

To get a list of cabinets

**Note:** If the `CABINET_ID_VALUE` is 0, it shows all cabinets in the list.

## JSON Successful CABINETS Response
Note that when the response is successful, the `ErrorCount` value is blank. 

```
{
    "root": {
        "errorStatus": {
            "List_Count": "1",
            "ErrorCount": "",
            "wd_Error_RCID": "",
            "wd_Error_RCTX": "",
            "wd_Error_MSG": "",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "Error": ""
        },
        "data": [
            {
                "L#": "1",
                "PGID": 14,
                "LIST": "14",
                "Name": "Accounting",
                "RO": "0",
                "DO": "0",
                "DC": "0",
                "DM": "0",
                "SV": "1",
                "PJ": "0",
                "AA": "0",
                "Fields": [
                    {
                        "FIELD": "Field #1",
                        "NAME": "Client",
                        "ACTIVE": 1,
                        "EDITOK": 1,
                        "ENTREQ": 1,
                        "LINKED": 0,
                        "SUBDIR": 1,
                        "PRIVAT": 0,
                        "WDUSER": 0,
                        "LOCKED": 0,
                        "MMDDYY": 0,
                        "VERIFY": 1,
                        "RETENT": 1,
                        "LENGTH": 5
                    },
                    {
                        "FIELD": "Field #2",
                        "NAME": "Year",
                        "ACTIVE": 1,
                        "EDITOK": 1,
                        "ENTREQ": 1,
                        "LINKED": 0,
                        "SUBDIR": 0,
                        "PRIVAT": 0,
                        "WDUSER": 0,
                        "LOCKED": 0,
                        "MMDDYY": 0,
                        "VERIFY": 1,
                        "RETENT": 0,
                        "LENGTH": 4
                    },
                    {
                        "FIELD": "Field #3",
                        "NAME": "Doctype",
                        "ACTIVE": 1,
                        "EDITOK": 1,
                        "ENTREQ": 1,
                        "LINKED": 0,
                        "SUBDIR": 1,
                        "PRIVAT": 0,
                        "WDUSER": 0,
                        "LOCKED": 0,
                        "MMDDYY": 0,
                        "VERIFY": 1,
                        "RETENT": 0,
                        "LENGTH": 8
                    },
                    {
                        "FIELD": "Field #4",
                        "NAME": "0",
                        "ACTIVE": 0,
                        "EDITOK": 0,
                        "ENTREQ": 0,
                        "LINKED": 0,
                        "SUBDIR": 0,
                        "PRIVAT": 0,
                        "WDUSER": 0,
                        "LOCKED": 0,
                        "MMDDYY": 0,
                        "VERIFY": 0,
                        "RETENT": 0,
                        "LENGTH": 0
                    },
                    {
                        "FIELD": "Field #5",
                        "NAME": "0",
                        "ACTIVE": 0,
                        "EDITOK": 0,
                        "ENTREQ": 0,
                        "LINKED": 0,
                        "SUBDIR": 0,
                        "PRIVAT": 0,
                        "WDUSER": 0,
                        "LOCKED": 0,
                        "MMDDYY": 0,
                        "VERIFY": 0,
                        "RETENT": 0,
                        "LENGTH": 0
                    },
                    {
                        "FIELD": "Field #6",
                        "NAME": "Typist",
                        "ACTIVE": 1,
                        "EDITOK": 1,
                        "ENTREQ": 1,
                        "LINKED": 0,
                        "SUBDIR": 0,
                        "PRIVAT": 0,
                        "WDUSER": 1,
                        "LOCKED": 0,
                        "MMDDYY": 0,
                        "VERIFY": 1,
                        "RETENT": 0,
                        "LENGTH": 8
                    },
                    {
                        "FIELD": "Field #7",
                        "NAME": "0",
                        "ACTIVE": 0,
                        "EDITOK": 0,
                        "ENTREQ": 0,
                        "LINKED": 0,
                        "SUBDIR": 0,
                        "PRIVAT": 0,
                        "WDUSER": 0,
                        "LOCKED": 0,
                        "MMDDYY": 0,
                        "VERIFY": 0,
                        "RETENT": 0,
                        "LENGTH": 0
                    }
                ]
            }
        ]
    }
}

```
## JSON Failed CABINETS Response
Note that when the response has failed, the `ErrorCount` value has a number, the `RCTX` value determines what the error is. The Worldox API always returns a `200` status even on failure. 

```

"root": {
        "errorStatus": {
            "List_Count": "",
            "ErrorCount": "1",
            "wd_Error_RCID": "8740",
            "wd_Error_RCTX": "WDRC_SID_INVALID",
            "wd_Error_MSG": "WDRC_SID_INVALID",
            "wd_Error_VAR": "wd_SID",
            "wd_Error_VAL": "GZtxRsXj2$2B8MnPlwt8pRFspAvTvLfEtgw0nQWOFs$2BIUTozTGBsr1WTxc6oY$3Dn",
            "Error": [
                {
                    "wd_Error_RCID": "8740",
                    "wd_Error_RCTX": "WDRC_SID_INVALID",
                    "wd_Error_MSG": "WDRC_SID_INVALID",
                    "wd_Error_VAR": "wd_SID",
                    "wd_Error_VAL": "GZtxRsXj2$2B8MnPlwt8pRFspAvTvLfEtgw0nQWOFs$2BIUTozTGBsr1WTxc6oY$3Dn"
                }
            ]
        },
        "data": [
            {
                "L#": "%:L#%",
                "PGID":%Cabinet_ID%,
                "LIST": "%:Cabinet_LIST%",
                "Name": "%:Cabinet_NAME%",
                "BP": "%:Cabinet_BASEPATH%",
                "RO": "%:Cabinet_READONLY%",
                "DO": "%:Cabinet_DENYOPEN%",
                "DC": "%:Cabinet_DENYCOPY%",
                "DM": "%:Cabinet_DENYMOVE%",
                "Fields":%Cabinet_FIELDS%
            }
        ]
    }
}

```

