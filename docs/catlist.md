CATLIST
=======

The CATLIST command lists the categories for a given path.

[CATLIST Example](#catlist-example)

[CATLIST Parameters](#catlist-parameters)

[JSON Successful CATLIST Response](#json-successful-catlist-response)

[JSON Failed CATLIST Response](#json-failed-catlist-response)

## CATLIST Example

```
/cgi-bin/wdwebcgi.exe?CATLIST&wd\_SID={{session}}
```

## CATLIST Parameters

`wd_SID`

The Worldox session ID

wd\_File\_Path\_Value

The path to look up categories in

HTMLOnOK

This is the page to return on a successful call to CATLIST.

v4\\categories\\categories-list.json

**Note:** api is deprecated but still can be used. Going forward v4 is the best practice.

HTMLOnFail

This is the page to return on a failed CATLIST.

```
v4\\categories\\categories-list.json
```

**Note:** api is deprecated but still can be used. Going forward v4 is the best practice.

_**[![up_arrow.gif](assets/images/up_arrow.gif "up_arrow.gif")](#)**_

## JSON Successful CATLIST Response

{

    "root": {

        "errorStatus": {

            "List\_ID": "x22FD1B8",

            "List\_Count": "22",

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

                "L": "1",

                "R": "16",

                "CN": "5D28B72E0.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "API Tester CATMAKE",

                "CI": "/cgi-bin/WDCATS/Internal/Category01.ico"

            },

            {

                "L": "2",

                "R": "17",

                "CN": "5D28A0870.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "API Tester CATMAKE",

                "CI": "/cgi-bin/WDCATS/Internal/Category01.ico"

            },

            {

                "L": "3",

                "R": "7",

                "CN": "5D2DE5000.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "API Tester CATMAKE",

                "CI": "/cgi-bin/WDCATS/Internal/Category01.ico"

            },

            {

                "L": "4",

                "R": "8",

                "CN": "5D2CA03C0.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "API Tester CATMAKE",

                "CI": "/cgi-bin/WDCATS/Internal/Category01.ico"

            },

            {

                "L": "5",

                "R": "9",

                "CN": "5D2C969C0.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "API Tester CATMAKE",

                "CI": "/cgi-bin/WDCATS/Internal/Category01.ico"

            },

            {

                "L": "6",

                "R": "10",

                "CN": "5D2C7B830.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "API Tester CATMAKE",

                "CI": "/cgi-bin/WDCATS/Internal/Category01.ico"

            },

            {

                "L": "7",

                "R": "11",

                "CN": "5D2C7AA60.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "API Tester CATMAKE",

                "CI": "/cgi-bin/WDCATS/Internal/Category01.ico"

            },

            {

                "L": "8",

                "R": "12",

                "CN": "5D2C7A010.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "API Tester CATMAKE",

                "CI": "/cgi-bin/WDCATS/Internal/Category01.ico"

            },

            {

                "L": "9",

                "R": "13",

                "CN": "5D2C76C70.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "API Tester CATMAKE",

                "CI": "/cgi-bin/WDCATS/Internal/Category01.ico"

            },

            {

                "L": "10",

                "R": "14",

                "CN": "5D28D7020.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "API Tester CATMAKE",

                "CI": "/cgi-bin/WDCATS/Internal/Category01.ico"

            },

            {

                "L": "11",

                "R": "15",

                "CN": "5D28B9470.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "API Tester CATMAKE",

                "CI": "/cgi-bin/WDCATS/Internal/Category01.ico"

            },

            {

                "L": "12",

                "R": "2",

                "CN": "5E6082190.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "electr�nico, s�lo del men� Kepl�w",

                "CI": ""

            },

            {

                "L": "13",

                "R": "6",

                "CN": "5DF9FBAE0.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "NEW CATE 1",

                "CI": ""

            },

            {

                "L": "14",

                "R": "4",

                "CN": "5D234BC70.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "OMG! IT DOESN\\"T WORK... AHHHHHH!!!",

                "CI": "/cgi-bin/WDCATS/Internal/Category06.ico"

            },

            {

                "L": "15",

                "R": "3",

                "CN": "5D2741220.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "soloBEANzz",

                "CI": "/cgi-bin/WDCATS/Network and Security/businessman\_view.ico"

            },

            {

                "L": "16",

                "R": "1",

                "CN": "5D28B8B70.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "Test make CATEGORY",

                "CI": "/cgi-bin/WDCATS/Internal/Category01.ico"

            },

            {

                "L": "17",

                "R": "5",

                "CN": "5D2370B00.15x51615",

                "TAB\_NAME": "Personal",

                "TAB\_BBID": "2147483788",

                "TAB\_FLAG": "8192",

                "CD": "Testing omg!!!!!",

                "CI": "/cgi-bin/WDCATS/Internal/Category04.ico"

            },

            {

                "L": "18",

                "R": "18",

                "CN": "57FFDD100.5xBACB4",

                "TAB\_NAME": "Public",

                "TAB\_BBID": "2147483789",

                "TAB\_FLAG": "4096",

                "CD": "Depo Exhibits",

                "CI": "/cgi-bin/WDCATS/Internal/Category04.ico"

            },

            {

                "L": "19",

                "R": "21",

                "CN": "57FFDCB10.5xBACB4",

                "TAB\_NAME": "Public",

                "TAB\_BBID": "2147483789",

                "TAB\_FLAG": "4096",

                "CD": "Discovery",

                "CI": "/cgi-bin/WDCATS/Internal/Category05.ico"

            },

            {

                "L": "20",

                "R": "19",

                "CN": "57FFDCFF0.5xBACB4",

                "TAB\_NAME": "Public",

                "TAB\_BBID": "2147483789",

                "TAB\_FLAG": "4096",

                "CD": "Executed",

                "CI": "/cgi-bin/WDCATS/Internal/Category10.ico"

            },

            {

                "L": "21",

                "R": "20",

                "CN": "57FFDCBF0.5xBACB4",

                "TAB\_NAME": "Public",

                "TAB\_BBID": "2147483789",

                "TAB\_FLAG": "4096",

                "CD": "Exhibits",

                "CI": "/cgi-bin/WDCATS/Internal/Category08.ico"

            },

            {

                "L": "22",

                "R": "22",

                "CN": "57FFCF340.5xBACB4",

                "TAB\_NAME": "Public",

                "TAB\_BBID": "2147483789",

                "TAB\_FLAG": "4096",

                "CD": "Research",

                "CI": "/cgi-bin/WDCATS/Internal/Category01.ico"

            }

        \]

    }

}

## JSON Failed CATLIST Response

```
{

    "root": {

        "errorStatus": {

            "List\_ID": "",

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

                "L": "%:L#%",

                "R": "%:R#%",

                "CN": "%:CAT\_ID%",

                "TAB\_NAME": "%:CAT\_TAB\_NAME%",

                "TAB\_BBID": "%:CAT\_TAB\_BBID%",

                "TAB\_FLAG": "%:CAT\_TAB\_FLAG%",

                "CD": "%:CAT\_NAME%",

                "CI": "%:CAT\_ICON%"

            }

        \]

    }

}
```
