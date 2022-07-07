21	PREVIEW
The PREVIEW command enables you to view the Worldox session.
21.1	PREVIEW Example
/cgi-bin/wdwebcgi.exe?VIEWFILE+wd_SID={{session}}
21.2	Parameters
{Worldox Web Domain} 
	Is the domain name
wd_SID
	Is the session ID
{Worldox Web User Session)
	Is the variable
HTMLOnOK
This is the page to return on a successful call to PREVIEW.
v4\fileActions\Previewer.json
Note: api is deprecated but still can be used. Going forward v4 is the best practice.
HTMLOnFail
This is the page to return on a failed PREVIEW.
v4\fileActions\Previewer.json
Note: api is deprecated but still can be used. Going forward v4 is the best practice.
wd_LIST_ID
The Worldox list ID
wd_LIST_recnum
The record number of the selected file
OFFSETCOUNT
The position on the file list
wd_VIEW_JPEG_PATH
The Worldox Web URL to preview file. 
For example, https://phoenix.wdsaas.com:443/^PATH^
21.3	JSON Successful PREVIEW Response
Note that when the response is successful, the ErrorCount value is blank. 
{
    "root": {
        "data": {
            "fileLoc": "/cgi-bin/WDSIDS/EHgRICvIKW4FNzZGxI%242Fxw6XR7Ag0Y5zbpsntEjhfiLLdCTZkz%242BaFbdWCx%242F4%243D/VIEW/005/00060/0140/VIEW_000.HTM",
            "FileNme": "2001%20natural%20gas%20forecast%20%2800001197x51615%29.MSG"
        },
        "errorStatus": {
            "ErrorCount": "",
            "wd_Error_RCID": "",
            "wd_Error_RCTX": "",
            "wd_Error_MSG": "",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "wd_Error_DOCID": "",
            "wd_Error_DOCNAME": "",
            "req_ID": "",
            "Error": ""
        }
    }
}
21.4	JSON Failed PREVIEW Response
Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  
{
    "root": {
        "data": {
            "message": "0=wd_List_Offset(48)"
        },
        "errorStatus": {
            "ErrorCount": "1",
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
