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
    gTopicId = "0_28";
  
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
<meta name="OriginalFile" content="2FSET (A1061937x80C7).DOCX"/>
<meta name="generator" content="Adobe RoboHelp 2020"/>
<title>2FSET</title>
<link rel="StyleSheet" href="assets/css/htmlhelp.css" type="text/css"/>
<style type="text/css">/*<![CDATA[*/
A:visited {
	color: #954F72;
}
A:link {
	color: #0000ff;
}
/*]]>*/</style>
<meta name="rh-index-keywords" content="Two Factor Authentication (2FA),2FA,ADD command,EDIT command,DELETE command,SET commands for Two Factor Authentication (2FA),“2FA”,“two factor authentication”,SET commands:for two factor authentication”,“POST requests”,email address"/></head>

<body style="word-wrap: break-word;">
  <div class="topic-header rh-hide" id="rh-topic-header" onclick="rh._.goToFullLayout()">
    <div class="logo">
    </div>
    <div class="nav">
      <div class="title" title="2FSET">
        <span>2FSET</span>
      </div>
      <div class="gotohome" title="Click here to see this page in full context">
        <span>Click here to see this page in full context</span>
      </div>
    </div>
  </div>
  <div class="topic-header-shadow rh-hide" id="rh-topic-header-shadow"></div>



<h1>2FSET: ADD/EDIT/DELETE: Two Factor Authentication (2FA)</h1>
<p><b>Note:</b> You will need Worldox Web 3.0 Rev: 140311 or newer to use 
 this API command.</p>
<p>You can use the ADD, EDIT and DELETE SET commands to add, edit or delete 
 devices, email addresses and or cell phone numbers associated to accounts 
 that use two factor authentication (2FA). These are POST requests.</p>
<p class="Note"><b><span style="color: #000000;">Note:</span></b> <span style="color: #000000;">All POST requests that require a session require 
 the session to be decoded either on the Body or as Parameter on the URL.</span></p>
<p class="Bullet_list"><a href="#2FSET_Examples">2FSET_Examples</a></p>
<p class="Bullet_list"><a href="#Add_a_Record">Add_a_Record</a></p>
<p class="Bullet_list"><a href="#JSON_Successful_Add_a_Record_JSON_Response">JSON_Successful_Add_a_Record_JSON_Response</a></p>
<p class="Bullet_list"><a href="#JSON_Failed_Add_a_Record_JSON_Response">JSON_Failed_Add_a_Record_JSON_Response</a></p>
<p class="Bullet_list"><a href="#Delete_a_Record">Delete_a_Record</a></p>
<p class="Bullet_list"><a href="#JSON_Successful_Delete_a_Record_JSON_Response">JSON_Successful_Delete_a_Record_JSON_Response</a></p>
<p class="Bullet_list"><a href="#JSON_Failed_Delete_a_Record_JSON_Response">JSON_Failed_Delete_a_Record_JSON_Response</a></p>
<p class="Bullet_list"><a href="#Edit_a_Record">Edit_a_Record</a></p>
<p class="Bullet_list"><a href="#JSON_Successful_Edit_a_Record_JSON_Response">JSON_Successful_Edit_a_Record_JSON_Response</a></p>
<p class="Bullet_list"><a href="#JSON_Failed_Edit_a_Record_JSON_Response">JSON_Failed_Edit_a_Record_JSON_Response</a></p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h2> </h2>
<h2><a id="2FSET_Examples"></a>2FSET Examples</h2>
<h3><a id="Add_a_Record"></a>Add a Record</h3>
<p>To add a record:</p>
<p><b>1</b>: Make a POST request to </p>
<p class="Code"><span class="Hyperlink">http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION}+HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json</span></p>
<p>Pass the following into the body:</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_SendToAddr</span></span>: 
 {Your email or cell phone # (number) of choice}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_SENDOBJECT</span></span>: 
 {What this action is for, e.g., Worldox}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_SENDACTION</span></span>: 
 {Why this action is, e.g., Worldox Web Authentication}</p>
<p>Once submitted and successful, the Response should return a Ref ID. 
 An email or text will be sent with an access code. Both are needed for 
 the next step.</p>
<p><img src="2FSET_(A1061937x80C7)_files/image001.png" alt="" title="" width="530" height="161" border="0"/></p>
<p><b>2</b>: Make another POST request to the same API (shown below) but 
 change the <b>Body</b>. </p>
<p class="Code"><span class="Hyperlink">http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION}</span> 
 +HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_WORLDOXREF:</span></span> 
 {REF ID from previous response}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_ACCESSCODE</span></span>: 
 {Access code from email or text}</p>
<p><b>3</b>: Make a third POST request to the same API but change the Body 
 once again.</p>
<p class="Code"><span class="Hyperlink">http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION}</span> 
 +HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_RecAddress</span></span>: 
 {The email or cell phone # that will be stored}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_RecContact</span></span>: 
 {the email or cell phone #’s description}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_RecEnabled</span></span>: 
 {1 if the record should be enabled and 0 if the record is disabled}</p>
<p>Once successful, a new item should be added to the list.</p>
<p> </p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h4><a id="JSON_Successful_Add_a_Record_JSON_Response"></a>JSON Successful 
 Add a Record JSON Response</h4>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">{</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;root&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;errorStatus&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_ID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_Count&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ErrorCount&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Error&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        },</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;data&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Ref&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Worldox 5FFC-B161&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;AC&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Send&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;*****er@*****ox.***&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;RMT&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;69.112.37.92&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe; 
	 font-size: 9.0pt; font-family: Consolas; color: #000000;">}</p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"> </p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h4><a id="JSON_Failed_Add_a_Record_JSON_Response"></a>JSON Failed Add 
 a Record JSON Response</h4>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">{</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;root&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;errorStatus&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_ID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_Count&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515; background: #ffff00;">&quot;ErrorCount&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000; background: #ffff00;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5; background: #ffff00;">&quot;1&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000; background: #ffff00;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Error&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: [</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;8030&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCTX&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;WDRC_2FA_ADDRESS_UNDEFINED&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_MSG&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Undefined Address\n\n\nThe email address entered for two factor authentication is not defined.\n\n\n\n\nOK\n&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAL&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            ]</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        },</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;data&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Ref&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;AC&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Send&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;RMT&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;69.112.37.92&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">}</span></p>
<p> </p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h3><a id="Delete_a_Record"></a>Delete a Record</h3>
<p>Make a POST request to the following API: </p>
<p class="Code"><span class="Hyperlink">http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION}</span> 
 +HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json</p>
<p>Pass the following into the body:</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_List_RecNum:</span></span> 
 {The Rec Number you retrieved from 2FGET}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_List_ID:</span></span> 
 {The List Number you retrieved from 2FGET}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_RecContract:</span></span> 
 {Description of email or cell phone #}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_RecEnabled:</span></span> 
 {DELETE}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_RecAddress:</span></span> 
 {Cell phone # or email}</p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h4><a id="JSON_Successful_Delete_a_Record_JSON_Response"></a>JSON Successful 
 Delete a Record JSON Response</h4>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">{</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;root&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;errorStatus&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_ID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;x256FAC8&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_Count&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ErrorCount&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Error&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        },</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;data&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Ref&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;AC&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Send&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;RMT&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;69.112.37.92&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">}</span></p>
<p>]</p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h4><span style="text-underline: none;"><a id="JSON_Failed_Delete_a_Record_JSON_Response"></a></span>JSON 
 Failed Delete a Record JSON Response</h4>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">{</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;root&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;errorStatus&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_ID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;x256B2F8&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_Count&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515; background: #ffff00;">&quot;ErrorCount&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000; background: #ffff00;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5; background: #ffff00;">&quot;1&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000; background: #ffff00;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Error&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: [</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;8740&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCTX&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;WDRC_SID_INVALID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_MSG&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;WDRC_SID_INVALID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;wd_SID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAL&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;null&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            ]</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        },</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;data&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Ref&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;AC&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Send&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;RMT&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;69.112.37.92&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">}</span></p>
<p> </p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h3><a id="Edit_a_Record"></a>Edit a Record</h3>
<p>To edit an existing record, there are a couple of steps.</p>
<p><b>1</b>: Make a POST request to the following API:</p>
<p class="Code"><span class="Hyperlink">http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION}+HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json</span></p>
<p>Depending upon the Description and/or whether the enabled/disabled item 
 has changed, this is the only step you need to update the record. Pass 
 the following into the <b>Body</b>.</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_List_RecNum:</span></span> 
 {The Rec Number you retrieved from 2FGET}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_List_ID:</span></span> 
 {The List Number you retrieved from 2FGET}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_RecContract:</span></span> 
 {Description of email or cell phone #}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_RecEnabled:</span></span> 
 {1 whether the record should be enabled and 0 if the record is disabled}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_RecAddress:</span></span> 
 {Cell phone # or email}</p>
<p>If the enabled cell phone #/email and/or Description has changed, you 
 will need to do the following steps. Pass the following into the <b>Body</b>:</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_SendToAddr:</span></span> 
 {Your email or cell phone # of choice}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_SENDOBJECT:</span></span> 
 {What this action is for e.g Worldox}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_SENDACTION:</span></span> 
 {Why this action is e.g Worldox Web Authentication}</p>
<p>Once submitted and successful, the Response should return a Ref ID. 
 An email or text will be sent with an access code. Both are needed for 
 the next step.</p>
<p><b>2</b>: Make another POST request to the same API but change the <b>Body</b>.</p>
<p class="Code"><span class="Hyperlink">http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION}</span> 
 +HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_WORLDOXREF:</span></span> 
 {REF ID from previous response},</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_ACCESSCODE:</span></span> 
 {Access code from email or text}</p>
<p><b>3</b>: Make a third POST request to the same API but change the <b>Body</b> 
 once again.</p>
<p class="Code"><span class="Hyperlink">http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FSET+wd_SID={SESSION}</span> 
 +HTMLOnOk=/v4/authentication/setTwoFactorDevice.json+HTMLOnFail=/v4/authentication/setTwoFactorDevice.json</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_List_RecNum:</span></span> 
 {The Rec Number you retrieved from 2FGET}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_List_ID:</span></span> 
 {The List Number you retrieved from 2FGET}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_RecContract:</span></span> 
 {Description of email or cell phone #}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_RecEnabled:</span></span> 
 {1 if the record should be enabled and 0 if the record is disabled}</p>
<p><span class="Code"><span style="font-size: 10.0pt;">wd_2FA_RecAddress:</span></span> 
 {Cell phone # or email}</p>
<span style="font-size: 11.0pt; font-family: Calibri, sans-serif;"><br style="clear: all;" clear="all"/>
</span> 
<p style="margin: 0in;"> </p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h4><a id="JSON_Successful_Edit_a_Record_JSON_Response"></a>JSON Successful 
 Edit a Record JSON Response</h4>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">{</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;root&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;errorStatus&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_ID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_Count&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ErrorCount&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Error&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        },</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;data&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Ref&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Worldox 5FFF-5042&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;AC&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Send&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;*****er@*****ox.***&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;RMT&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;69.112.37.92&quot;</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        }</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    }</span></p>
<p style="margin-bottom: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">}</span></p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h4><a id="JSON_Failed_Edit_a_Record_JSON_Response"></a>JSON Failed Edit 
 a Record JSON Response</h4>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">{</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;root&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;errorStatus&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_ID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;x214E1A8&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_Count&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515; background: #ffff00;">&quot;ErrorCount&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000; background: #ffff00;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5; background: #ffff00;">&quot;1&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000; background: #ffff00;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Error&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: [</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;8375&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCTX&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;WDRC_LISTID_INVALID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_MSG&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Invalid list ID issue\n\n\nInvalid list ID, click Refresh to update your file list.\n\n\n\ncloseCircle, wdErrorIco\nRefresh\nCancel&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAL&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            ]</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        },</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;data&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Ref&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;AC&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Send&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;RMT&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;69.112.37.92&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">}</span></p>
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
