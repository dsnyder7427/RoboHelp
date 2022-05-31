//<!\[CDATA\[ function reDo() { if (innerWidth != origWidth || innerHeight != origHeight) location.reload(); } if ((parseInt(navigator.appVersion) == 4) && (navigator.appName == "Netscape")) { origWidth = innerWidth; origHeight = innerHeight; onresize = reDo; } onerror = null; //\]\]> /\*<!\[CDATA\[\*/ < !-- div.WebHelpPopupMenu { position: absolute; left: 0px; top: 0px; z-index: 4; visibility: hidden; } p.WebHelpNavBar { text-align: right; } --> /\*\]\]>\*/ //<!\[CDATA\[ gRootRelPath = "."; gCommonRootRelPath = "."; gTopicId = "0\_27"; //\]\]>       2FGET  /\*<!\[CDATA\[\*/ A:visited { color: #954F72; } A:link { color: #0000ff; } /\*\]\]>\*/ 

2FGET

Click here to see this page in full context

2FGET: Two Factor Authentication (2FA)
======================================

**Note:** You will need Worldox Web 3.0 Rev: 140311 or newer to use this API command.

Gets the list. This is a GET request.

To elaborate, the 2FGET command retrieves a list of devices, email addresses and cell phone numbers used for two factor authentication (2FA). Two factor authentication can protect Worldox Web 3.x from unauthorized access by setting a program password or using a password combined with an access code.  Worldox Web 3.x will prompt an end user to enter it when you first launch it or if you unlocked your PC or device and need to regain access to Worldox Web 3.x.

[2FGET\_Example](#2FGET_Example)

[2FGET\_Parameters](#2FGET_Parameters)

[JSON\_Successful\_2FGET\_Response](#JSON_Successful_2FGET_Response)

[JSON\_Failed\_2FGET\_Response](#JSON_Failed_2FGET_Response)

_**[![up_arrow.gif](assets/images/up_arrow.gif "up_arrow.gif")](#)**_

2FGET Example
-------------

http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FGET+wd\_SID={SESSION} +HTMLOnOk=/v4/authentication/twoFactorDevice.json+HTMLOnFail=/v4/authentication/twoFactorDevice.json

This will return the entire list.

2FGET Parameters
----------------

wd\_SID

The Worldox session ID

HTMLOnOK

This is the page to be returned on a success.

HTMLOnFAIL

This is the page to be returned on a failure.

WD\_List\_Filter

Redact>0. If Redact is set to be less than 0, contact information is shown.

Redact>1. If Redact is set to be less than 1, asterisks appear in the output to hide email addresses or phone numbers.

If

WD\_List\_Filter=Redact>0

Contact information (email addresses or cell phone numbers) are shown:

{  
"Rec": "1",  
"L": "2",  
"ADDR": "(555) 279-5579",  
"ADDR.ASIS": "+1555279579",  
"ADDR.VIEW": "(555) 279-5579",  
"NAME": "John’s Cell",  
"FLAG": "Yes"  
},

If

WD\_List\_Filter=Redact>1

Email addresses are hidden with asterisks:

{​​​​​​​​  
"Rec":"1",  
"L":"2",  
"ADDR":"(\*\*\*) \*\*\*-\*\*79",  
"ADDR.ASIS":"+\*\*\*\*\*\*\*\*\*79",  
"ADDR.VIEW":"(\*\*\*) \*\*\*-\*\*79",  
"NAME":"John’s Cell",  
"FLAG":"Yes"  
}​​​​​​​​,

_**[![up_arrow.gif](assets/images/up_arrow.gif "up_arrow.gif")](#)**_

JSON Successful 2FGET Response
------------------------------

{

    "root": {

        "errorStatus": {

            "List\_ID": "x211D3D8",

            "List\_Count": "2",

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

                "Rec": "1",

                "L": "1",

                "ADDR": "(551) 655-5721",

                "ADDR.ASIS": "+15516555721",

                "ADDR.VIEW": "(551) 655-5721",

                "FLAG": "Yes"

            },

            {

                "Rec": "2",

                "L": "2",

                "ADDR": "dsnyder@worldox.com",

                "ADDR.ASIS": "dsnyder@worldox.com",

                "ADDR.VIEW": "dsnyder@worldox.com",

                "FLAG": "Yes"

            }

        \]

    }

}

_**[![up_arrow.gif](assets/images/up_arrow.gif "up_arrow.gif")](#)**_

JSON Failed 2FGET Response
--------------------------

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

            "wd\_Error\_VAL": "pQG7rtsguFSwdhnaBLtpvrtxOwZoDI4bGO3EnXdTMRHy1bqg1FctD7A6Gw8$3Dkopkp\[wy",

            "Error": \[

                {

                    "wd\_Error\_RCID": "8740",

                    "wd\_Error\_RCTX": "WDRC\_SID\_INVALID",

                    "wd\_Error\_MSG": "WDRC\_SID\_INVALID",

                    "wd\_Error\_VAR": "wd\_SID",

                    "wd\_Error\_VAL": "pQG7rtsguFSwdhnaBLtpvrtxOwZoDI4bGO3EnXdTMRHy1bqg1FctD7A6Gw8$3Dkopkp\[wy"

                }

            \]

        },

        "data": \[

            {

                "Rec": "%:R#%",

                "L": "%:L#%",

                "ADDR": "%:ADDR%",

                "ADDR.ASIS": "%:ADDR.ASIS%",

                "ADDR.VIEW": "%:ADDR.VIEW%",

                "NAME": "%:NAME%",

                "FLAG": "%:FLAG%"

            }

        \]

    }

}

_**[![up_arrow.gif](assets/images/up_arrow.gif "up_arrow.gif")](#)**_

//<!\[CDATA\[ var mailSubject = 'Useful online help topic'; var mailBody = 'This online help page might help: ' + location.href; var mailDisplay = 'Email this topic to another user.'; document.write( '<a href="mailto:yourname@yourSite.com' + '?subject=' + escape(mailSubject) + '&body=' + escape(mailBody) + '">' + mailDisplay + '<\\/a>' ); //\]\]>
