---
layout: default
title: 2FSET
nav_order: 24
---

# 2FSET: ADD/EDIT/DELETE: TWO FACTOR AUTHENTICATION (2FA)

**Note:** You will need Worldox Web 3.0 Rev: 140311 or newer to use this API command.

You can use the ADD, EDIT and DELETE SET commands to add, edit or delete devices, email addresses and or cell phone numbers associated to accounts that use two factor authentication (2FA). These are POST requests.

**Note:** All POST requests that require a session require the session to be decoded either on the Body or as Parameter on the URL.

[2FSET Examples](#2fset-examples)

[2FSET Parameters](#2fset-parameters)

[JSON Successful 2FSET Response](#json-successful-2fset-response)

[JSON Failed 2FSET Response](#json-failed-2fset-response)

## 2FSET Examples

### Add a Record

To add a record:

1: Make a POST request to 

`http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION}+HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json`

Pass the following into the body:

`wd_2FA_SendToAddr:` {Your email or cell phone # (number) of choice}

`wd_2FA_SENDOBJECT:` {What this action is for, e.g., Worldox}

`wd_2FA_SENDACTION:` {Why this action is, e.g., Worldox Web Authentication}

Once submitted and successful, the Response should return a Ref ID. An email or text will be sent with an access code. Both are needed for the next step.


