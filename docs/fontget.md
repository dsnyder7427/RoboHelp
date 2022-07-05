---
layout: default
title: FONTGET
nav_order: 13
---

# FONTGET
 The FONTGET command returns all the active fonts for the logged in user. This is a GET request.

[FONTGET Example](#fontget-example)

[FONTGET Parameters](#fontget-parameters)

[JSON Successful FONTGET Response](#json-successful-fontget-response)

[JSON Failed FONTGET Response](#json-failed-fontget-response)

## FONTGET Example

`{{url}}/cgi-bin/wdwebcgi.exe?FONTGET&wd_SID=' + {Worldox Web User Session) &html=/v4/font/getfonts.json`

## FONTGET Parameters

`HTML`

     This is the page to return on a call to FONTGET.

     `v4\font\getfonts.json`

`wd_SID`
     
     The Worldox session ID.


The output will look something like this for each font item type:
```
{
     "L#":"2",                //can be ignored, it is just positionally the # in this list
     "bUNDERLINE":0,          //Is the font underlined
     "bITALIC":0,             //Is the font Italic
     "bSTRIKEOUT":0,          //does the font have strikeout
     "cyLINE":32,             //can be ignored
     "cyTEXTMIN":15,          //can be ignored
     "cyTEXTMAX":15,          //can be ignored
     "cyTOPDENT":1,           //can be ignored
     "crTEXT":5131854,        //The decimal equivalent of the color (when converted it
                              should be the RGB in hex 0x4E4E4E)
     "RC.LEFT":0,             //Padding left
     "RC.RIGHT":0,            //Padding right
     "RC.TOP":7,              //Padding Top
     "RC.BOTTOM":17,          //padding bottom
     "szLABEL":"File List Comments",       //section Label. Corresponds to line in   
     customize dialog:  
     "szFACENAME":"Calibri",  //Font name
     "uFONTID":0,             //Font ID
     "uPOINTSIZE":100,        //Font point size
     "uWEIGHT":400,           //font weight
     "uHEIGHT":-13            //Font height
}
```
 
## JSON Successful FONTS Response

Note that when the response is successful, the ErrorCount value is blank. 
```
{
    "root": {
        "Extra": {
            "MaxCommentLines": "3"
        },
        "errorStatus": {
            "List_Count": "13",
            "ErrorCount": "",
            "wd_Error_RCID": "",
            "wd_Error_RCTX": "",
            "wd_Error_MSG": "",
            "wd_Error_VAR": "",
            "wd_Error_VAL": "",
            "Val": ""
        },
        "data": [
            {
                "L#": "1",
                "bUNDERLINE": "0",
                "bITALIC": "0",
                "bSTRIKEOUT": "0",
                "cyLINE": "14",
                "cyTEXTMIN": "14",
                "cyTEXTMAX": "14",
                "cyTOPDENT": "0",
                "crTEXT": "#000000",
                "RC.LEFT": "0",
                "RC.RIGHT": "0",
                "RC.TOP": "0",
                "RC.BOTTOM": "15",
                "szLABEL": "File List Bottom Line",
                "szFACENAME": "Tahoma",
                "uFONTID": "32",
                "uPOINTSIZE": "9",
                "uWEIGHT": "400",
                "uHEIGHT": "-12",
                "bVISIBLE": 0
            },
            {
                "L#": "2",
                "bUNDERLINE": "0",
                "bITALIC": "0",
                "bSTRIKEOUT": "0",
                "cyLINE": "26",
                "cyTEXTMIN": "15",
                "cyTEXTMAX": "15",
                "cyTOPDENT": "1",
                "crTEXT": "#4E4E4E",
                "RC.LEFT": "0",
                "RC.RIGHT": "0",
                "RC.TOP": "4",
                "RC.BOTTOM": "4",
                "szLABEL": "File List Comments",
                "szFACENAME": "Calibri",
                "uFONTID": "31",
                "uPOINTSIZE": "10",
                "uWEIGHT": "400",
                "uHEIGHT": "-13",
                "bVISIBLE": 1
            },
            {
                "L#": "3",
                "bUNDERLINE": "0",
                "bITALIC": "0",
                "bSTRIKEOUT": "0",
                "cyLINE": "26",
                "cyTEXTMIN": "15",
                "cyTEXTMAX": "15",
                "cyTOPDENT": "1",
                "crTEXT": "#FF8040",
                "RC.LEFT": "0",
                "RC.RIGHT": "0",
                "RC.TOP": "4",
                "RC.BOTTOM": "0",
                "szLABEL": "File List WorkFlow Value",
                "szFACENAME": "Calibri",
                "uFONTID": "30",
                "uPOINTSIZE": "10",
                "uWEIGHT": "700",
                "uHEIGHT": "-13",
                "bVISIBLE": 1
            },
            {
                "L#": "4",
                "bUNDERLINE": "0",
                "bITALIC": "0",
                "bSTRIKEOUT": "0",
                "cyLINE": "26",
                "cyTEXTMIN": "14",
                "cyTEXTMAX": "14",
                "cyTOPDENT": "2",
                "crTEXT": "#4E4E4E",
                "RC.LEFT": "0",
                "RC.RIGHT": "0",
                "RC.TOP": "4",
                "RC.BOTTOM": "0",
                "szLABEL": "File List WorkFlow Label",
                "szFACENAME": "Calibri",
                "uFONTID": "29",
                "uPOINTSIZE": "9",
                "uWEIGHT": "400",
                "uHEIGHT": "-12",
                "bVISIBLE": 1
            },
            {
                "L#": "5",
                "bUNDERLINE": "0",
                "bITALIC": "0",
                "bSTRIKEOUT": "0",
                "cyLINE": "26",
                "cyTEXTMIN": "15",
                "cyTEXTMAX": "15",
                "cyTOPDENT": "1",
                "crTEXT": "#FF8040",
                "RC.LEFT": "0",
                "RC.RIGHT": "0",
                "RC.TOP": "4",
                "RC.BOTTOM": "0",
                "szLABEL": "File List TextHits Value",
                "szFACENAME": "Calibri",
                "uFONTID": "28",
                "uPOINTSIZE": "10",
                "uWEIGHT": "700",
                "uHEIGHT": "-13",
                "bVISIBLE": 1
            },
            {
                "L#": "6",
                "bUNDERLINE": "0",
                "bITALIC": "0",
                "bSTRIKEOUT": "0",
                "cyLINE": "26",
                "cyTEXTMIN": "15",
                "cyTEXTMAX": "15",
                "cyTOPDENT": "1",
                "crTEXT": "#4E4E4E",
                "RC.LEFT": "0",
                "RC.RIGHT": "0",
                "RC.TOP": "4",
                "RC.BOTTOM": "0",
                "szLABEL": "File List TextHits Label",
                "szFACENAME": "Calibri",
                "uFONTID": "27",
                "uPOINTSIZE": "10",
                "uWEIGHT": "400",
                "uHEIGHT": "-13",
                "bVISIBLE": 1
            },
            {
                "L#": "7",
                "bUNDERLINE": "0",
                "bITALIC": "0",
                "bSTRIKEOUT": "0",
                "cyLINE": "26",
                "cyTEXTMIN": "15",
                "cyTEXTMAX": "15",
                "cyTOPDENT": "1",
                "crTEXT": "#FF8040",
                "RC.LEFT": "0",
                "RC.RIGHT": "0",
                "RC.TOP": "4",
                "RC.BOTTOM": "0",
                "szLABEL": "File List Checkout Value",
                "szFACENAME": "Calibri",
                "uFONTID": "26",
                "uPOINTSIZE": "10",
                "uWEIGHT": "700",
                "uHEIGHT": "-13",
                "bVISIBLE": 1
            },
            {
                "L#": "8",
                "bUNDERLINE": "0",
                "bITALIC": "0",
                "bSTRIKEOUT": "0",
                "cyLINE": "26",
                "cyTEXTMIN": "14",
                "cyTEXTMAX": "14",
                "cyTOPDENT": "2",
                "crTEXT": "#4E4E4E",
                "RC.LEFT": "0",
                "RC.RIGHT": "0",
                "RC.TOP": "4",
                "RC.BOTTOM": "0",
                "szLABEL": "File List Checkout Label",
                "szFACENAME": "Calibri",
                "uFONTID": "25",
                "uPOINTSIZE": "9",
                "uWEIGHT": "400",
                "uHEIGHT": "-12",
                "bVISIBLE": 1
            },
            {
                "L#": "9",
                "bUNDERLINE": "0",
                "bITALIC": "0",
                "bSTRIKEOUT": "0",
                "cyLINE": "23",
                "cyTEXTMIN": "15",
                "cyTEXTMAX": "15",
                "cyTOPDENT": "0",
                "crTEXT": "#4E4E4E",
                "RC.LEFT": "0",
                "RC.RIGHT": "0",
                "RC.TOP": "4",
                "RC.BOTTOM": "0",
                "szLABEL": "File List Props Value",
                "szFACENAME": "Calibri",
                "uFONTID": "24",
                "uPOINTSIZE": "10",
                "uWEIGHT": "400",
                "uHEIGHT": "-13",
                "bVISIBLE": 1
            },
            {
                "L#": "10",
                "bUNDERLINE": "0",
                "bITALIC": "0",
                "bSTRIKEOUT": "0",
                "cyLINE": "23",
                "cyTEXTMIN": "15",
                "cyTEXTMAX": "15",
                "cyTOPDENT": "0",
                "crTEXT": "#4E4E4E",
                "RC.LEFT": "0",
                "RC.RIGHT": "0",
                "RC.TOP": "4",
                "RC.BOTTOM": "0",
                "szLABEL": "File List Props Label",
                "szFACENAME": "Calibri",
                "uFONTID": "23",
                "uPOINTSIZE": "10",
                "uWEIGHT": "700",
                "uHEIGHT": "-13",
                "bVISIBLE": 1
            },
            {
                "L#": "11",
                "bUNDERLINE": "0",
                "bITALIC": "0",
                "bSTRIKEOUT": "0",
                "cyLINE": "28",
                "cyTEXTMIN": "18",
                "cyTEXTMAX": "18",
                "cyTOPDENT": "0",
                "crTEXT": "#4E4E4E",
                "RC.LEFT": "0",
                "RC.RIGHT": "0",
                "RC.TOP": "5",
                "RC.BOTTOM": "0",
                "szLABEL": "File List Profiles",
                "szFACENAME": "Calibri",
                "uFONTID": "22",
                "uPOINTSIZE": "11",
                "uWEIGHT": "400",
                "uHEIGHT": "-15",
                "bVISIBLE": 0
            },
            {
                "L#": "12",
                "bUNDERLINE": "0",
                "bITALIC": "0",
                "bSTRIKEOUT": "0",
                "cyLINE": "28",
                "cyTEXTMIN": "15",
                "cyTEXTMAX": "15",
                "cyTOPDENT": "1",
                "crTEXT": "#4E4E4E",
                "RC.LEFT": "0",
                "RC.RIGHT": "0",
                "RC.TOP": "5",
                "RC.BOTTOM": "5",
                "szLABEL": "File List Group Value",
                "szFACENAME": "Calibri",
                "uFONTID": "21",
                "uPOINTSIZE": "10",
                "uWEIGHT": "400",
                "uHEIGHT": "-13",
                "bVISIBLE": 1
            },
            {
                "L#": "13",
                "bUNDERLINE": "0",
                "bITALIC": "0",
                "bSTRIKEOUT": "0",
                "cyLINE": "29",
                "cyTEXTMIN": "19",
                "cyTEXTMAX": "19",
                "cyTOPDENT": "0",
                "crTEXT": "#710000",
                "RC.LEFT": "0",
                "RC.RIGHT": "0",
                "RC.TOP": "5",
                "RC.BOTTOM": "5",
                "szLABEL": "File List Group Label",
                "szFACENAME": "Calibri",
                "uFONTID": "20",
                "uPOINTSIZE": "12",
                "uWEIGHT": "400",
                "uHEIGHT": "-16",
                "bVISIBLE": 1
            }
        ]
    }
}
```
 
## JSON Failed FONTS Response

Note that when the response has failed, the ErrorCount value has a number, the RCTX value determines what the error is. The Worldox API always returns a 200 status even on failure.  

```
{
    "root": {
        "Extra": {
            "MaxCommentLines": ""
        },
        "errorStatus": {
            "List_Count": "",
            "ErrorCount": "1",
            "wd_Error_RCID": "8740",
            "wd_Error_RCTX": "WDRC_SID_INVALID",
            "wd_Error_MSG": "WDRC_SID_INVALID",
            "wd_Error_VAR": "wd_SID",
            "wd_Error_VAL": "null",
            "Val": ""
        },
        "data": [
            {
                "L#": "%:L#%",
                "Label": "%:LABEL%",
                "bUNDERLINE": "%:bUNDERLINE%",
                "bITALIC": "%:bITALIC%",
                "bSTRIKEOUT": "%:bSTRIKEOUT%",
                "cyLINE": "%:cyLINE%",
                "cyTEXTMIN": "%:cyTEXTMIN%",
                "cyTEXTMAX": "%:cyTEXTMAX%",
                "cyTOPDENT": "%:cyTOPDENT%",
                "crTEXT": "%:crTEXT%",
                "RC.LEFT": "%:RC.LEFT%",
                "RC.RIGHT": "%:RC.RIGHT%",
                "RC.TOP": "%:RC.TOP%",
                "RC.BOTTOM": "%:RC.BOTTOM%",
                "szLABEL": "%:szLABEL%",
                "szFACENAME": "%:szFACENAME%",
                "uFONTID": "%:uFONTID%",
                "uPOINTSIZE": "%:uPOINTSIZE%",
                "uWEIGHT": "%:uWEIGHT%",
                "uHEIGHT": "%:uHEIGHT%",
                "bVISIBLE":%:bVISIBLE%
            }
        ]
    }
}
```
