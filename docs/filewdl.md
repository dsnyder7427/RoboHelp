# FILEWDL (UPDATE TEMP WDL)
The FILEWDL command adds or removes a file from the .wdl project. 


## FILEWDL Required Parameters
wd_list_ID
	Is the list ID of a project
wd_SID
	Is the Worldox session ID
Html1
	Should be /v4/errorlog/error.json or something similar since the API will only return whether it worked or not
12.2	Optional Parameters
wd_List_RecNum
	Is the existing record number of an item in the wdl if you want to remove it
wd_File_PathFile_Value
	Is the file to add
12.3	JSON Successful FILEWDL Response
Note that when the response is successful, the ErrorCount value is blank. 
{
    "root": {
        "data": {
            "XN": "",
            "LN": "x26BC0D0",
            "RN": "0",
            "FN": "",
            "C": "",
            "PF": "\\\\#\\005\\00001\\0010\\00016627.docx",
            "V": "",
            "O": "",
            "1C": "",
            "1D": "",
            "2C": "",
            "2D": "",
            "3C": "",
            "3D": "",
            "4C": "",
            "4D": "",
            "5C": "",
            "5D": "",
            "6C": "",
            "6D": "",
            "7C": "",
            "7D": "",
            "ID": "",
            "S": "",
            "I": "",
            "AT": "",
            "CT": "",
            "UT": "",
            "PM": "",
            "DN": "",
            "CHKOUT_TO_NAME": "",
            "List_ID": "x26BC0D0"
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

12.4	JSON Failed FILEWDL Response
Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  
{
    "root": {
        "data": {
            "XN": "",
            "LN": "x26B8438",
            "RN": "0",
            "FN": "",
            "C": "",
            "PF": "%WDTEMPPATH%\\$WD89F008955FFEFBE200000026.WDL\n \n",
            "V": "",
            "O": "",
            "1C": "",
            "1D": "",
            "2C": "",
            "2D": "",
            "3C": "",
            "3D": "",
            "4C": "",
            "4D": "",
            "5C": "",
            "5D": "",
            "6C": "",
            "6D": "",
            "7C": "",
            "7D": "",
            "ID": "",
            "S": "",
            "I": "",
            "AT": "",
            "CT": "",
            "UT": "",
            "PM": "",
            "DN": "",
            "CHKOUT_TO_NAME": "",
            "List_ID": "x26B8438"
        },
        "errorStatus": {
            "ErrorCount": "1",
            "wd_Error_RCID": "8275",
            "wd_Error_RCTX": "WDRC_FILE_NOT_FOUND",
            "wd_Error_MSG": "File Search Failure\n\n\nThe file could not be found.\nTry to enter the file name again.\nIf the file still is not found, it may have been deleted from Worldox.\n\n\nOK\n",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "wd_Error_DOCID": "",
            "wd_Error_DOCNAME": "",
            "req_ID": "",
            "Error": [
                {
                    "wd_Error_RCID": "8275",
                    "wd_Error_RCTX": "WDRC_FILE_NOT_FOUND",
                    "wd_Error_MSG": "File Search Failure\n\n\nThe file could not be found.\nTry to enter the file name again.\nIf the file still is not found, it may have been deleted from Worldox.\n\n\nOK\n",
                    "wd_Error_VAR": "",
                    "wd_Error_VAL": ""
                }
            ]
        }
    }
}
