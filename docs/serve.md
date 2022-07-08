---
layout: default
title: SERVE
nav_order: 20
---

# SERVE

The SERVE command returns a data list for the logged in user. Note: HASH and REREAD are SERVE commands. 

[SERVE Example](#serve-example)

[SERVE Parameters](#serve-parameters)

[SERVE Examples for Different Pages](#serve-examples-for-different-pages)

[](#)

[JSON Successful SERVE Response](#json-successful-serve-response)

[JSON Failed SERVE Response](#json-failed-serve-response)

## SERVE Example

`{{url}}/cgi-bin/wdwebcgi.exe?SERVE&wd_SID={{session}}&html={{page}}`

## Parameters

`HTML`
	
	This is the page to be served.
	
	`\v4\filelist\rereadrecord.json`
	
Pass in

Take 1

`Skip`
	Is the offset of the list
		
`wd_List_RecNum`
	
	The recnum of file

`wd_List_ID`

	Is the list ID of file
	
## SERVE Examples for Different Pages

There are many different pages that can be served. Please note while reading the following examples that some of these pages have additional parameters and others do not.

