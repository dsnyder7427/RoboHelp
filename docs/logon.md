
LOGON
=====

The LOGON command logs you into Worldox Web. It is a POST request.

[LOGON\_Endpoint]

[Request\_Body](#Request_Body)

[JSON\_Successful\_LOGON\_Response](#JSON_Successful_LOGON_Response)

[JSON\_Failed\_LOGON\_Response](#JSON_Failed_LOGON_Response)

 LOGON Endpoint
---------------

POST /cgi-bin/wdwebcgi.exe?LOGON/cgi-bin/wdwebcgi.exe?LOGON

_**[![up_arrow.gif](assets/images/up_arrow.gif "up_arrow.gif")](#)**_

Request Body
------------

HTMLOnOK

This is the page to return on a successful call to LOGON.

v4\\authentication\\login.json

**Note:** api is deprecated but still can be used. Going forward v4 is the best practice.

HTMLOnFail

This is the page to return on a failed LOGON.

V4\\authentication\\login.json

**Note:** api is deprecated but still can be used. Going forward v4 is the best practice.

wd\_User\_Code\_Value

Worldox Web Server User Code

wd\_User\_Password\_Value

Worldox Web User Password

_**[![up_arrow.gif](assets/images/up_arrow.gif "up_arrow.gif")](#)**_

### JSON Successful LOGON Response

Note that when the response is successful, the ErrorCount value is blank.

"root": {

        "data": {

            "session": "mK2JN75CKK2NN643lsNiLAyWKr%242Ff2XB%242BvFn3ljbYex%242FEahK7OTXML5Daei0%243D",

            "servername": "\_5D839152\_51615\_F",

            "user": "QC User1",

            "name": "QC1",

            "email": "qc1@worldox.com",

            "uploadFolder": "/cgi-bin/WDSIDS/mK2JN75CKK2NN643lsNiLAyWKr$2Ff2XB$2BvFn3ljbYex$2FEahK7OTXML5Daei0$3D/SAVE/upload-file.asp",

            "uploadFolderJSON": "/cgi-bin/WDSIDS/mK2JN75CKK2NN643lsNiLAyWKr$2Ff2XB$2BvFn3ljbYex$2FEahK7OTXML5Daei0$3D/SAVE/upload-file-json.asp",

            "ownerInital": "",

            "ErrorCount": "",

            "wd\_Error\_MSG": "",

            "Firm": "World Software Corporation",

            "OnlineHelp": "https://www.worldox.com/WEB3HELP/!SSL!/WebHelp/Introduction.htm",

            "WWTroubleShoot": "https://www.worldox.com/WEB3DOCS/Worldox%20Web%203.0%20Basics%20and%20Troubleshooting.pdf",

            "IISVER": "20201120",

            "AuthMethod": "b",

            "Graph": "3e58cb3b-1d02-4f55-b6a8-c113d1c2102c",

            "rsClient": "a0a571e5b8f0447c0c6c1cc9d00d7dee46ef6f1d97990c513aabcc04d260c7a9",

            "rsRedirect": "https://phoenix.wdsaas.com",

            "rsSecret": "ce0ea030382921255f858ccc2dbd748c308cfcd58878ce3e4d40c9ec3e4ad138"

        },

        "errorStatus": {

            "ErrorCount": "",

            "wd\_Error\_RCID": "",

            "wd\_Error\_RCTX": "",

            "wd\_Error\_MSG": "",

            "wd\_Error\_VAR": "",

            "wd\_Error\_VAL": "",

            "wd\_Error\_DOCID": "",

            "wd\_Error\_DOCNAME": "",

            "req\_ID": "",

            "Error": ""

        }

    }

}

_**[![up_arrow.gif](assets/images/up_arrow.gif "up_arrow.gif")](#)**_

### JSON Failed LOGON Response

Note that when the response has failed, the ErrorCount value has a number.

{

    "root": {

        "data": {

            "session": "",

            "servername": "\*",

            "user": "",

            "name": "qc1@worldox.com",

            "email": "",

            "uploadFolder": "/upload-file.asp",

            "uploadFolderJSON": "/upload-file-json.asp",

            "ownerInital": "",

            "ErrorCount": "1",

            "wd\_Error\_MSG": "WDRC\_LOGON\_USER\_PASSWORD\_INVALID",

            "Firm": "World Software Corporation",

            "OnlineHelp": "https://www.worldox.com/WEB3HELP/!SSL!/WebHelp/Introduction.htm",

            "WWTroubleShoot": "https://www.worldox.com/WEB3DOCS/Worldox%20Web%203.0%20Basics%20and%20Troubleshooting.pdf",

            "IISVER": "20201120",

            "AuthMethod": "b",

            "Graph": "3e58cb3b-1d02-4f55-b6a8-c113d1c2102c",

            "rsClient": "a0a571e5b8f0447c0c6c1cc9d00d7dee46ef6f1d97990c513aabcc04d260c7a9",

            "rsRedirect": "https://phoenix.wdsaas.com",

            "rsSecret": "ce0ea030382921255f858ccc2dbd748c308cfcd58878ce3e4d40c9ec3e4ad138"

        },

        "errorStatus": {

            "ErrorCount": "1",

            "wd\_Error\_RCID": "8435",

            "wd\_Error\_RCTX": "WDRC\_LOGON\_USER\_PASSWORD\_INVALID",

            "wd\_Error\_MSG": "WDRC\_LOGON\_USER\_PASSWORD\_INVALID",

            "wd\_Error\_VAR": "wd\_USER\_NAME\_VALUE",

            "wd\_Error\_VAL": "The user name or password is incorrect. (WINRC#1326)",

            "wd\_Error\_DOCID": "",

            "wd\_Error\_DOCNAME": "",

            "req\_ID": "",

            "Error": \[

                {

                    "wd\_Error\_RCID": "8435",

                    "wd\_Error\_RCTX": "WDRC\_LOGON\_USER\_PASSWORD\_INVALID",

                    "wd\_Error\_MSG": "WDRC\_LOGON\_USER\_PASSWORD\_INVALID",

                    "wd\_Error\_VAR": "wd\_USER\_NAME\_VALUE",

                    "wd\_Error\_VAL": "The user name or password is incorrect. (WINRC#1326)"

                }

            \]

        }

    }

}

