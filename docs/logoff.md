32	LOGOFF
The LOGOFF command closes the Worldox Web Session.
32.1	LOGOFF Example
/cgi-bin/wdwebcgi.exe?LOGOFF&wd_SID={{session}}
32.2	Parameters
{Worldox Web Domain} 
	Is the domain name
wd_SID
	Is the session ID
{Worldox Web User Session)
	Is the variable
HTMLOnOK
This is the page to return on a successful call to LOGOFF.
v4 \authentication\logoffSucc.json
Note: api is deprecated but still can be used. Going forward v4 is the best practice.
HTMLOnFail
This is the page to return on a failed LOGOFF.
v4 \authentication\logoffFail.json
Note: api is deprecated but still can be used. Going forward v4 is the best practice.
32.3	JSON Successful LOGOFF Response
{
    "root": {
        "data": {
            "loggedOff": "successfully"
        }
    }
}
Note: There is no failed response for LOGOFF.

