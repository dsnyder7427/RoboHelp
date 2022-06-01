CABINETS
========

[CABINETS\_Example](#CABINETS_Example)

[CABINETS\_Parameters](#CABINETS_Parameters)

[JSON\_Successful\_CABINETS\_Response](#JSON_Successful_CABINETS_Response)

[JSON\_Failed\_CABINETS\_Response](#JSON_Failed_CABINETS_Response)

_**[![up_arrow.gif](assets/images/up_arrow.gif "up_arrow.gif")](#)**_

### CABINETS Example

The CABINETS command retrieves a list of Cabinets.

/cgi-bin/wdwebcgi.exe?CABINETS&wd\_SID{{session}}&html=/v4/cabinets/cabinets.json&wd\_CABINET\_ID\_VALUE={{List of Cabinet IDs}}

### CABINETS Parameters

/api/cabinets/ cabinets.json

To get a list of cabinets

**Note:** If the CABINET\_ID\_VALUE is 0, it shows all cabinets in the list.

_**[![up_arrow.gif](assets/images/up_arrow.gif "up_arrow.gif")](#)**_

### JSON Successful CABINETS Response

{

    "root": {

        "errorStatus": {

            "List\_Count": "1",

            "ErrorCount": "",

            "wd\_Error\_RCID": "",

            "wd\_Error\_RCTX": "",

            "wd\_Error\_MSG": "",

            "wd\_Error\_VAR": "",

            "wd\_Error\_VAL": "",

            "Error": ""

        },

        "data": \[

            {

                "L#": "1",

                "PGID": 14,

                "LIST": "14",

                "Name": "Accounting",

                "RO": "0",

                "DO": "0",

                "DC": "0",

                "DM": "0",

                "SV": "1",

                "PJ": "0",

                "AA": "0",

                "Fields": \[

                    {

                        "FIELD": "Field #1",

                        "NAME": "Client",

                        "ACTIVE": 1,

                        "EDITOK": 1,

                        "ENTREQ": 1,

                        "LINKED": 0,

                        "SUBDIR": 1,

                        "PRIVAT": 0,

                        "WDUSER": 0,

                        "LOCKED": 0,

                        "MMDDYY": 0,

                        "VERIFY": 1,

                        "RETENT": 1,

                        "LENGTH": 5

                    },

                    {

                        "FIELD": "Field #2",

                        "NAME": "Year",

                        "ACTIVE": 1,

                        "EDITOK": 1,

                        "ENTREQ": 1,

                        "LINKED": 0,

                        "SUBDIR": 0,

                        "PRIVAT": 0,

                        "WDUSER": 0,

                        "LOCKED": 0,

                        "MMDDYY": 0,

                        "VERIFY": 1,

                        "RETENT": 0,

                        "LENGTH": 4

                    },

                    {

                        "FIELD": "Field #3",

                        "NAME": "Doctype",

                        "ACTIVE": 1,

                        "EDITOK": 1,

                        "ENTREQ": 1,

                        "LINKED": 0,

                        "SUBDIR": 1,

                        "PRIVAT": 0,

                        "WDUSER": 0,

                        "LOCKED": 0,

                        "MMDDYY": 0,

                        "VERIFY": 1,

                        "RETENT": 0,

                        "LENGTH": 8

                    },

                    {

                        "FIELD": "Field #4",

                        "NAME": "0",

                        "ACTIVE": 0,

                        "EDITOK": 0,

                        "ENTREQ": 0,

                        "LINKED": 0,

                        "SUBDIR": 0,

                        "PRIVAT": 0,

                        "WDUSER": 0,

                        "LOCKED": 0,

                        "MMDDYY": 0,

                        "VERIFY": 0,

                        "RETENT": 0,

                        "LENGTH": 0

                    },

                    {

                        "FIELD": "Field #5",

                        "NAME": "0",

                        "ACTIVE": 0,

                        "EDITOK": 0,

                        "ENTREQ": 0,

                        "LINKED": 0,

                        "SUBDIR": 0,

                        "PRIVAT": 0,

                        "WDUSER": 0,

                        "LOCKED": 0,

                        "MMDDYY": 0,

                        "VERIFY": 0,

                        "RETENT": 0,

                        "LENGTH": 0

                    },

                    {

                        "FIELD": "Field #6",

                        "NAME": "Typist",

                        "ACTIVE": 1,

                        "EDITOK": 1,

                        "ENTREQ": 1,

                        "LINKED": 0,

                        "SUBDIR": 0,

                        "PRIVAT": 0,

                        "WDUSER": 1,

                        "LOCKED": 0,

                        "MMDDYY": 0,

                        "VERIFY": 1,

                        "RETENT": 0,

                        "LENGTH": 8

                    },

                    {

                        "FIELD": "Field #7",

                        "NAME": "0",

                        "ACTIVE": 0,

                        "EDITOK": 0,

                        "ENTREQ": 0,

                        "LINKED": 0,

                        "SUBDIR": 0,

                        "PRIVAT": 0,

                        "WDUSER": 0,

                        "LOCKED": 0,

                        "MMDDYY": 0,

                        "VERIFY": 0,

                        "RETENT": 0,

                        "LENGTH": 0

                    }

                \]

            }

        \]

    }

}

_**[![up_arrow.gif](assets/images/up_arrow.gif "up_arrow.gif")](#)**_

### JSON Failed CABINETS Response

"root": {

        "errorStatus": {

            "List\_Count": "",

            "ErrorCount": "1",

            "wd\_Error\_RCID": "8740",

            "wd\_Error\_RCTX": "WDRC\_SID\_INVALID",

            "wd\_Error\_MSG": "WDRC\_SID\_INVALID",

            "wd\_Error\_VAR": "wd\_SID",

            "wd\_Error\_VAL": "GZtxRsXj2$2B8MnPlwt8pRFspAvTvLfEtgw0nQWOFs$2BIUTozTGBsr1WTxc6oY$3Dn",

            "Error": \[

                {

                    "wd\_Error\_RCID": "8740",

                    "wd\_Error\_RCTX": "WDRC\_SID\_INVALID",

                    "wd\_Error\_MSG": "WDRC\_SID\_INVALID",

                    "wd\_Error\_VAR": "wd\_SID",

                    "wd\_Error\_VAL": "GZtxRsXj2$2B8MnPlwt8pRFspAvTvLfEtgw0nQWOFs$2BIUTozTGBsr1WTxc6oY$3Dn"

                }

            \]

        },

        "data": \[

            {

                "L#": "%:L#%",

                "PGID":%Cabinet\_ID%,

                "LIST": "%:Cabinet\_LIST%",

                "Name": "%:Cabinet\_NAME%",

                "BP": "%:Cabinet\_BASEPATH%",

                "RO": "%:Cabinet\_READONLY%",

                "DO": "%:Cabinet\_DENYOPEN%",

                "DC": "%:Cabinet\_DENYCOPY%",

                "DM": "%:Cabinet\_DENYMOVE%",

                "Fields":%Cabinet\_FIELDS%

            }

        \]

    }

}
