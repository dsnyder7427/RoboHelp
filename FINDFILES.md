<?xml version="1.0" encoding="utf-8" ?>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml"><head>

  <script type="text/javascript" language="JavaScript">
    //<![CDATA[
    function reDo() {
      if (innerWidth != origWidth || innerHeight != origHeight)
        location.reload();
    }
    if ((parseInt(navigator.appVersion) == 4) && (navigator.appName == "Netscape")) {
      origWidth = innerWidth;
      origHeight = innerHeight;
      onresize = reDo;
    }
    onerror = null;
  //]]>
  </script>
  <style type="text/css">/*<![CDATA[*/

    < !-- div.WebHelpPopupMenu {
      position: absolute;
      left: 0px;
      top: 0px;
      z-index: 4;
      visibility: hidden;
    }

    p.WebHelpNavBar {
      text-align: right;
    }

    -->
  
/*]]>*/</style>

  <script type="text/javascript">//<![CDATA[

    gRootRelPath = ".";
    gCommonRootRelPath = ".";
    gTopicId = "0_12";
  
//]]></script>

  <script type="text/javascript" src="./template/scripts/rh.min.js"></script>
  <script type="text/javascript" src="./template/scripts/common.min.js"></script>
  <script type="text/javascript" src="./template/scripts/topic.min.js"></script>
  <script type="text/javascript" src="./template/scripts/topicwidgets.min.js"></script>
<script type="text/javascript" src="./whxdata/projectsettings.js"></script>
  <link rel="stylesheet" type="text/css" href="./template/styles/topic.min.css"/>
  <link rel="stylesheet" type="text/css" href="./template/Blue_Worldox/topicheader.css"/>
  <meta name="topic-status" content="Draft"/>

<meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
<meta name="OriginalFile" content="FINDFILES.DOCX"/>
<meta name="generator" content="Adobe RoboHelp 2020"/>
<title>FINDFILES</title>
<link rel="StyleSheet" href="assets/css/htmlhelp.css" type="text/css"/>
<style type="text/css">/*<![CDATA[*/
A:visited {
	color: #800080;
}
A:link {
	color: #0000ff;
}
/*]]>*/</style>
<meta name="rh-index-keywords" content="searching for documents,finding files,Create Temp List command,FINDFILES command,Get List command,SORTFILES command"/></head>

<body style="word-wrap: break-word;">
  <div class="topic-header rh-hide" id="rh-topic-header" onclick="rh._.goToFullLayout()">
    <div class="logo">
    </div>
    <div class="nav">
      <div class="title" title="FINDFILES">
        <span>FINDFILES</span>
      </div>
      <div class="gotohome" title="Click here to see this page in full context">
        <span>Click here to see this page in full context</span>
      </div>
    </div>
  </div>
  <div class="topic-header-shadow rh-hide" id="rh-topic-header-shadow"></div>



<h1>FINDFILES (Get List, Create Temp List, SORTFILES)</h1>
<p>The FINDFILES command is the Worldox search command. It is a GET request. 
 It is sometimes referred to as GetList. <b>Note:</b> FINDFILES is used 
 for GetList and Create Temp list. SORTFILES is a separate command, but 
 it can use the same output as FINDFILES.</p>
<p class="Bullet_list"><a href="#FINDFILES_Example">FINDFILES_Example</a></p>
<p class="Bullet_list"><a href="#FINDFILES_Parameters____">FINDFILES_Parameters</a></p>
<p class="Bullet_list"><a href="#FINDFILES_Sort_Values">FINDFILES_Sort_Values</a></p>
<p class="Bullet_list"><a href="#1_4_JSON_Response_Keys">JSON_Response_Keys</a></p>
<p class="Bullet_list"><a href="#_JSON_Successful_FINDFILES_Response">JSON_Successful_FINDFILES_Response</a></p>
<p class="Bullet_list"><a href="#JSON_Failed_FINDFILES_Response">JSON_Failed_FINDFILES_Response</a></p>
<h2><a id="FINDFILES_Example"></a>FINDFILES Example</h2>
<p class="Code">{{url}}/cgi-bin/wdwebcgi.exe?FINDFILES&amp;wd_SID={{session}}&amp;html=/v4/filelist/fileList.json&amp;wd_FIND_QUERY={{findQuery}}&amp;skip=&amp;{{skip}}&amp;take={{take}}</p>
<p class="Code"> </p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h2><a id="FINDFILES_Parameters____"></a>FINDFILES Parameters  </h2>
<p class="Code">HTMLOnOK</p>
<p style="text-indent: .5in;">This is the page to return on a successful 
 call to FINDFILES.</p>
<p class="Code" style="text-indent: .5in;">v4\filelist\fileList.json</p>
<p class="Note"><b><span style="font-size: 11.0pt; font-family: Calibri, sans-serif; 
						 color: windowtext;">Note:</span></b> api <span style="font-size: 11.0pt; font-family: Calibri, sans-serif; color: windowtext;">is 
 deprecated but still can be used. Going forward</span> v4 <span style="font-size: 11.0pt; 
	 font-family: Calibri, sans-serif; color: windowtext;">is the best 
 practice.</span></p>
<p class="Code">HTMLOnFail</p>
<p style="text-indent: .5in;">This is the page to return on a failed FINDFILES.</p>
<p class="Code" style="text-indent: .5in;">v4\filelist\fileList.json</p>
<p class="Note"><b><span style="font-size: 11.0pt; font-family: Calibri, sans-serif; 
						 color: windowtext;">Note:</span></b> api <span style="font-size: 11.0pt; font-family: Calibri, sans-serif; color: windowtext;">is 
 deprecated but still can be used. Going forward</span> v4 <span style="font-size: 11.0pt; 
	 font-family: Calibri, sans-serif; color: windowtext;">is the best 
 practice.</span></p>
<p class="Code">wd_FIND_QUERY</p>
<p style="text-indent: .5in;">Is the search used in the session authenticated 
 to the URL</p>
<p class="Code">Skip</p>
<p>                Is 
 where you start. 0 is the value.</p>
<p class="Code">Take</p>
<p style="margin-left: .5in;">Is set to 500, which is the current default. 
 <b>Note:</b> In the future, you can configure this to be a greater value.</p>
<p style="margin-left: .5in;"> </p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h2><a id="FINDFILES_Sort_Values"></a>FINDFILES Sort Values</h2>
<p class="Code">wd_file_sort_key1</p>
<p style="text-indent: .5in;">Is whatever the column ID is</p>
<p class="Code">wd_file_sort_dir1</p>
<p>                1 
 sorts the column in descending order</p>
<p>                0 
 sorts the column in ascending order</p>
<p class="Code">wd_File_Updated_Value</p>
<p class="Code">wd_File_Version_Value</p>
<p class="Code">wd_File_Size_Value</p>
<p class="Code">wd_File_Xname_Value</p>
<p class="Code">wd_File_FileName_Value</p>
<p class="Code"> </p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h2><a id="JSON_Response_Keys_for_FINDFILES"></a><a id="emailing_files" data-indexterm="emailing files"></a><a id="comments" data-indexterm="comments"></a><a id="Create_Temp_List_command" data-indexterm="Create Temp List command"></a><a id="FINDFILES_command:JSON_response_keys" data-indexterm="FINDFILES command:JSON response keys"></a><a id="Get_List_command" data-indexterm="Get List command"></a><a id="JSON_response_keys" data-indexterm="JSON response keys"></a><a id="1_4_JSON_Response_Keys"></a>JSON 
 Response Keys for FINDFILES</h2>
<p>The following table describes the available flags for wd_List_Rename_Flags.</p>
<table style="border: none; border-collapse: separate;" cellspacing="0">
	<tbody><tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: solid #000000 1.0px; 
			 border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="151"><p><b>JSON Key</b></p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: solid #000000 1.0px; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="180"><p><b>Slim 
		 Parameter</b></p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: solid #000000 1.0px; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="341"><p><b>Meaning</b></p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>“Description”</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%Xname%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>File description</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;DocId&quot;</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%DOCID%&quot;, </p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>File name</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;DateUpdated&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%wUPDATED%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>unixtimestamp of date updated</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Size&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%SIZE%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p style="text-autospace: none;">File size</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Comments&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%COMMENTS%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>File comments</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Version&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%VERSION%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Version number</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;I&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%wSTATUSID%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Numerical value of file status (checked-out 
		 etc.)</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;dwRC&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%dwRC%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Return code of the file (if it is missing from 
		 the file system)</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;stFl&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%wSTATUS_FLAGS%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Status flags #</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;stIc&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%wSTATUS_ICON%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Status icon #</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;HASH&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%H#%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Hash of every value above it</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;FilePath&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%UNCPG_PATHONLY%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Descriptive path of file</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;FilePathReal&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%UNCPG_PATHFILE%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Physical path of file</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;LN&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%L#%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>File offset</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;RN&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%R#%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>File record number</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;LID&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;^wd_List_ID^&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>List ID of current list</p>
		<p> </p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field1&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD1%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 1 code</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field1Desc&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD1DESC%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 1 description</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field1Name&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%Field1Name%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 1 name</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field2&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD2%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 2 code</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field2Desc&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD2DESC%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 2 description</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field2Name&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%Field2Name%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 2 name</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field3&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD3%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 3 code</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field3Desc&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD3DESC%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 3 description</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field3Name&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%Field3Name%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 3 name</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field4&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD4%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 4 code</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field4Desc&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD4DESC%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 4 description</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field4Name&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%Field4Name%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 4 name</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field5&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD5%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 5 code</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field5Desc&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD5DESC%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 5 description</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field5Name&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%Field5Name%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 5 name</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field6&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD6%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 6 code</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field6Desc&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD6DESC%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 6 description</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field6Name&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%Field6Name%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 6 name</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field7&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD7%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 7 code</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field7Desc&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FIELD7DESC%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 7 description</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Field7Name&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%Field67Name%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Field 7 name</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;AccessedDate&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%wACCESSED%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>unix timestamp of date accessed</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;DateCreated&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%wCREATED%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>unix timestamp of date created</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;PathMap&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%PATHMAP%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>“Hidden” path of file</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;ProfileGroupId&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%wGROUP%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Cabinet ID</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Cabinet&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%GROUP%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Cabinet name</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Location&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%PATH%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Descriptive path</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;Extension&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%EXT%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>File extension</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;OW&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%OWNERINIT%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Owner initials (last person to access the file</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;FF&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%FAVORITE%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Is this file a favorite? If so, how?</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;EFR&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%EMAIL_FR%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Email was from</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;ETO&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%EMAIL_TO%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Email was to</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;ECC&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%EMAIL_CC%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Email had CC</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;EBC&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%EMAIL_BCC%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Email had bcc</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;ETS&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%EMAIL_tSENT%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Time email was sent</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;ETR&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%EMAIL_tRCVD%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Time email was received</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;ERF&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%EMAIL_tRFDATE%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Received from date</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;ERW&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%EMAIL_RFWHO%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Received from person</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;EAD&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%EMAIL_ADDR%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Email from</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;szRC&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%szRC%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>dwRCs error text</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;CHKOUT_TO_PREF&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%CHKOUT_TO_PREF%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Part of the checked-out line</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;CHKOUT_TO_NAME&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%CHKOUT_TO_NAME%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Part of the checked-out line</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;CHKOUT_ON_PREF&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%CHKOUT_ON_PREF%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Part of the checked-out line</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;CHKOUT_ON_DATE&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%CHKOUT_ON_DATE%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Part of the checked-out line</p></td>
	</tr>
	<tr>
		<td style="vertical-align: top; border-left: solid #000000 1.0px; 
			 border-right: solid #000000 1.0px; border-top: none; border-bottom: solid #000000 1.0px; 
			 padding: 0in 5.4pt 0in 5.4pt; padding-left: 0px; padding-top: 0px; 
			 padding-right: 0px; padding-bottom: 0px;" width="151"><p>&quot;CHKOUT_TO_LINE&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="180"><p>&quot;%CHKOUT_TO_LINE%&quot;,</p></td>
		<td style="vertical-align: top; border-left: none; border-right: solid #000000 1.0px; 
			 border-top: none; border-bottom: solid #000000 1.0px; padding: 0in 5.4pt 0in 5.4pt; 
			 padding-left: 0px; padding-top: 0px; padding-right: 0px; padding-bottom: 0px;" width="341"><p>Full checked out-line</p></td>
	</tr>
</tbody></table>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h2><a id="_JSON_Successful_FINDFILES_Response"></a><a id="Create_Temp_List_command1" data-indexterm="Create Temp List command"></a><a id="FINDFILES_command" data-indexterm="FINDFILES command"></a><a id="Get_List_command1" data-indexterm="Get List command"></a><a id="1_5_JSON_Successful"> </a><span style="color: #ffffff;">JSON Successful FINDFILES Response</span></h2>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">{</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;root&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;errorStatus&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_ID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;x2304DA0&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_Count&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;3&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ErrorCount&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCTX&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_MSG&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAL&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Tab&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;10602:Find: Name=Excel ...&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Type&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;10602&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Title&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Find: Name=Excel ...&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Desc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Find: Name=Excel; using Quick Access &lt;Active&gt;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Desc_Loc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Find: Name=Excel; using Quick Access &lt;Active&gt;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Raw_Loc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;?E Excel | ?G 14;5;3;18;6 ?R D ?@Quick Access&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_True_Loc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;?E Excel | ?G 14;5;3;18;6 ?R D ?@Quick Access&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Groupings&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;0&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        },</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;data&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: [</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;XN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&lt;span class=&#39;selectedTxt&#39;&gt;Excel&lt;/span&gt; test.&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;00015655.xlsx&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;UPD&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1587490528&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;LSZ&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;8.6 KB&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;I&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;0&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;stFl&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;5&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;stIc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;0&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;HASH&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;x3357286E&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;EXT&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;XLSX&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;LN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;RN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;3&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CBID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;5&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FP&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;\\\\#\\005\\00001\\0010&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CRTD&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1587492000&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ACC&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1594663200&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FPR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;\\\\#\\005\\00001\\0010\\00015655.xlsx&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;PSD&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&lt;undefined&gt;&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            },</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;XN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&lt;span class=&#39;selectedTxt&#39;&gt;Excel&lt;/span&gt; test.&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;00015661.xlsx&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;UPD&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1587490528&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;LSZ&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;8.6 KB&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CM&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Copied.&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;I&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;0&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;stFl&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;5&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;stIc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;0&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;HASH&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;xAF06FCA3&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;EXT&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;XLSX&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;LN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;2&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;RN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;2&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CBID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;5&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FP&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;\\\\#\\005\\00001\\0050&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CRTD&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1587492000&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ACC&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1587492000&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FPR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;\\\\#\\005\\00001\\0050\\00015661.xlsx&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;PSD&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&lt;undefined&gt;&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            },</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;XN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Sutter &lt;span class=&#39;selectedTxt&#39;&gt;Excel&lt;/span&gt; Doc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;00015577.xlsx&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;UPD&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1584985444&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;LSZ&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;8.3 KB&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;I&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;0&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;stFl&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;5&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;stIc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;0&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;HASH&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;x11E76B0C&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;EXT&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;XLSX&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;LN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;3&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;RN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CBID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;5&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FP&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;\\\\#\\005\\00007\\0050&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CRTD&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1584986400&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ACC&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1584986400&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FPR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;\\\\#\\005\\00007\\0050\\00015577.xlsx&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;PSD&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&lt;undefined&gt;&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        ]</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">}</span></p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h3><a id="Note_about_Successful_JSON__FINDFILES__Response"></a><a id="Create_Temp_List_command2" data-indexterm="Create Temp List command"></a><a id="FINDFILES_command1" data-indexterm="FINDFILES command"></a><a id="Get_List_command2" data-indexterm="Get List command"></a><a id="1_6_Note_about"></a>Note 
 about Successful JSON (FINDFILES) Response</h3>
<p>Successful JSON output for FINDFILES can sometimes show an ErrorCount 
 of 1 if no data is returned. FINDFILES is used for folders, templates, 
 Favorites, filters and projects (WDL files).</p>
<p>The following example shows that a WDL was created. It is still successful 
 output even though an error says, <span style="font-size: 9.0pt; font-family: Consolas; 
										 color: #A31515;">wd_Error_RCTX&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;WDRC_ZERO_PROJECT_CLEAN.</span> 
 In this case, there are no files in the project.</p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">{</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;root&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;errorStatus&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_ID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;x257A1C8&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_Count&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;0&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515; background: #ffff00;">&quot;ErrorCount&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000; background: #ffff00;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5; background: #ffff00;">&quot;1&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000; background: #ffff00;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;9105&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515; background: #ffff00;">&quot;wd_Error_RCTX&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000; background: #ffff00;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5; background: #ffff00;">&quot;WDRC_ZERO_PROJECT_CLEAN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000; background: #ffff00;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_MSG&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Empty Project List\nYour project contains no files.\n\n\n\n\nProjectCollection, wdInfo\nWarning, wdWarningIco\n\nOk&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAL&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Tab&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;12011:New Project&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Title&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;New Project&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Desc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;New Project&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Desc_Loc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Project: New Project&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Raw_Loc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Project: C:\\Users\\QC4@WORLDOXQC.COM\\AppData\\Local\\Temp\\WBGX\\4736.2\\$WD89F008955FFCBC950000008D.WDL&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_True_Loc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Project: C:\\Users\\QC4@WORLDOXQC.COM\\AppData\\Local\\Temp\\WBGX\\4736.2\\$WD89F008955FFCBC950000008D.WDL&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Groupings&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;0&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Error&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: [</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;9105&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCTX&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;WDRC_ZERO_PROJECT_CLEAN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_MSG&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Empty Project List\nYour project contains no files.\n\n\n\n\nProjectCollection, wdInfo\nWarning, wdWarningIco\n\nOk&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAL&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            ]</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        },</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;data&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">}</span></p>
<p> </p>
<h3><a id="JSON_Failed_FINDFILES_Response"></a><a id="Create_Temp_List_command3" data-indexterm="Create Temp List command"></a><a id="FINDFILES_command2" data-indexterm="FINDFILES command"></a><a id="Get_List_command3" data-indexterm="Get List command"></a><a id="1_7_JSON_Failed"></a>JSON 
 Failed FINDFILES Response</h3>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">{</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;root&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;errorStatus&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_ID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_Count&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515; background: #ffff00;">&quot;ErrorCount&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000; background: #ffff00;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5; background: #ffff00;">&quot;1&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000; background: #ffff00;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;8740&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCTX&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;WDRC_SID_INVALID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_MSG&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;WDRC_SID_INVALID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;wd_SID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAL&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;YBWCWEmb24t19GDpPWf9VZwfrTxOBgbaG7JK5H8culn6nD$2Fk1hSqwabPijk$3Dn&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Tab&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;:&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Type&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Title&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Desc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Desc_Loc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Raw_Loc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_True_Loc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Groupings&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;0&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        },</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;data&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: [</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;XN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:Xname%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:DOCID%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;UPD&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:wUPDATED%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;LSZ&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:SIZE%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CM&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:COMMENTS%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;VER&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:VERSION%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;I&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:wSTATUSID%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;dwRC&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:dwRC%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;stFl&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:wSTATUS_FLAGS%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;stIc&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:wSTATUS_ICON%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CAT_ID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:CATS_JSON%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;HASH&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:H#%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FF&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:FAVORITE%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;EXT&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:EXT%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;LN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:L#%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;RN&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:R#%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CBID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:wGROUP%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FP&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:UNCPG_PATHONLY%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CRTD&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:wCREATED%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ACC&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:wACCESSED%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CHKOUT_TO_PREF&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:CHKOUT_TO_PREF%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CHKOUT_TO_NAME&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:CHKOUT_TO_NAME%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CHKOUT_ON_PREF&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:CHKOUT_ON_PREF%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CHKOUT_ON_DATE&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:CHKOUT_ON_DATE%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;CHKOUT_TO_LINE&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:CHKOUT_TO_LINE%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FPR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:UNCPG_PATHFILE%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;PSL&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%SHARED_LINK%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;PSU&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%SHARED_USER%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;PSD&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%SHARED_DATE%&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        ]</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">}</span></p>
<p> </p>
<p> </p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<p><script type="text/javascript">//<![CDATA[
var mailSubject = 'Useful online help topic'; 
var mailBody    = 'This online help page might help: ' + location.href; 
var mailDisplay = 'Email this topic to another user.'; 
document.write( 
    '<a href="mailto:yourname@yourSite.com' 
    + '?subject=' + escape(mailSubject) 
    + '&body=' + escape(mailBody) 
    + '">' + mailDisplay + '<\/a>' 
    );
//]]></script></p>

</body></html>
