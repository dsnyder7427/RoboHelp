---
layout: default
title: LOGOFF
nav_order: 29
---

# LOGOFF

The LOGOFF command closes the Worldox Web Session.

[LOGOFF Example](#logoff-example)

[LOGOFF Parameters](#logoff-parameters)

[JSON Successful LOGOFF Response](#json-successful-logoff-response)


## LOGOFF Example

/cgi-bin/wdwebcgi.exe?LOGOFF&wd_SID={{session}}

## LOGOFF Parameters

`{Worldox Web Domain}`

Is the domain name

`wd_SID`
	
Is the session ID

`{Worldox Web User Session)`

Is the variable

`HTMLOnOK`

This is the page to return on a successful call to LOGOFF.

`v4 \authentication\logoffSucc.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

`HTMLOnFail`

This is the page to return on a failed LOGOFF.

`v4 \authentication\logoffFail.json`

**Note:** `api` is deprecated but still can be used. Going forward v4 is the best practice.

## JSON Successful LOGOFF Response

```
{
    "root": {
        "data": {
            "loggedOff": "successfully"
        }
    }
}
```

**Note:** There is no failed response for LOGOFF.

