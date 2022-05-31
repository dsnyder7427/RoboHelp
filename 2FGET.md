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
    gTopicId = "0_27";
  
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
<meta name="OriginalFile" content="2FGET"/>
<meta name="generator" content="Adobe RoboHelp 2020"/>
<title>2FGET</title>
<link rel="StyleSheet" href="assets/css/htmlhelp.css" type="text/css"/>
<style type="text/css">/*<![CDATA[*/
A:visited {
	color: #954F72;
}
A:link {
	color: #0000ff;
}
/*]]>*/</style>
<meta name="rh-index-keywords" content="2FGET command,Two Factor Authentication (2FA),2FA,“2FA”,“GET requests”,“two factor authentication”,email address"/></head>

<body style="word-wrap: break-word;">
  <div class="topic-header rh-hide" id="rh-topic-header" onclick="rh._.goToFullLayout()">
    <div class="logo">
    </div>
    <div class="nav">
      <div class="title" title="2FGET">
        <span>2FGET</span>
      </div>
      <div class="gotohome" title="Click here to see this page in full context">
        <span>Click here to see this page in full context</span>
      </div>
    </div>
  </div>
  <div class="topic-header-shadow rh-hide" id="rh-topic-header-shadow"></div>



<h1>2FGET: Two Factor Authentication (2FA)</h1>
<p><b>Note:</b> You will need Worldox Web 3.0 Rev: 140311 or newer to use 
 this API command.</p>
<p>Gets the list. This is a GET request.</p>
<p>To elaborate, the 2FGET command retrieves a list of devices, email addresses 
 and cell phone numbers used for two factor authentication (2FA). Two factor 
 authentication can protect Worldox Web 3.x from unauthorized access by 
 setting a program password or using a password combined with an access 
 code.  Worldox Web 3.x will prompt an end user to enter it when 
 you first launch it or if you unlocked your PC or device and need to regain 
 access to Worldox Web 3.x.</p>
<p class="Bullet_list"><a href="#2FGET_Example">2FGET_Example</a></p>
<p class="Bullet_list"><a href="#2FGET_Parameters">2FGET_Parameters</a></p>
<p class="Bullet_list"><a href="#JSON_Successful_2FGET_Response">JSON_Successful_2FGET_Response</a></p>
<p class="Bullet_list"><a href="#JSON_Failed_2FGET_Response">JSON_Failed_2FGET_Response</a></p>
<p> </p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h2><a id="2FGET_Example"></a><a id="FGET_command" data-indexterm="2FGET command"></a><a id="“GET_requests”" data-indexterm="“GET requests”"></a><a id="“two_factor_authentication”" data-indexterm="“two factor authentication”"></a><a id="1_1_2FGET_Example"></a>2FGET Example</h2>
<p class="Code"><span class="Hyperlink">http://{DOMAIN}/cgi-bin/wdwebcgi.exe?2FGET+wd_SID={SESSION}</span> 
 +HTMLOnOk=/v4/authentication/twoFactorDevice.json+HTMLOnFail=/v4/authentication/twoFactorDevice.json</p>
<p class="Code"><span style="font-size: 11.0pt; font-family: Calibri, sans-serif; 
						 color: windowtext;">This will return the entire 
 list.</span></p>
<h2><a id="2FGET_Parameters"></a>2FGET Parameters</h2>
<p class="Code">wd_SID</p>
<p style="text-indent: .5in;">The Worldox session ID</p>
<p class="Code">HTMLOnOK</p>
<p style="text-indent: .5in;">This is the page to be returned on a success.</p>
<p class="Code">HTMLOnFAIL</p>
<p style="text-indent: .5in;">This is the page to be returned on a failure.</p>
<p class="Code"><span style="background: #ffffff;">WD_List_Filter</span><a id="“Redact_in_WD_List_Filter”" data-indexterm="“Redact in WD_List_Filter”"></a><a id="“RWD_List_Filter”" data-indexterm="“RWD_List_Filter”"></a><a name="WD_List_Filter" id="WD_List_Filter"></a></p>
<p style="text-indent: .5in;"><span class="Code"><span style="font-size: 9.0pt;">Redact&gt;0</span></span>. 
 If Redact is set to be less than<a id="“Redact_in_WD_List_Filter”1" data-indexterm="“Redact in WD_List_Filter”"></a><a id="IX_“Redact_in_WD_List_1"></a> 0, 
 contact information is shown.</p>
<p style="text-indent: .5in;"><span class="Code"><span style="font-size: 9.0pt;">Redact&gt;1</span></span>. 
 If Redact is set to be less than 1, asterisks appear in the output to 
 hide email addresses or phone numbers.</p>
<p>If</p>
<p class="Code">WD_List_Filter=Redact&gt;0</p>
<p>Contact information (email addresses or cell phone numbers) are shown:</p>
<p class="Code">{<br/>
&quot;Rec&quot;: &quot;1&quot;,<br/>
&quot;L&quot;: &quot;2&quot;,<br/>
&quot;ADDR&quot;: &quot;(555) 279-5579&quot;,<br/>
&quot;ADDR.ASIS&quot;: &quot;+1555279579&quot;,<br/>
&quot;ADDR.VIEW&quot;: &quot;(555) 279-5579&quot;,<br/>
&quot;NAME&quot;: &quot;John’s Cell&quot;,<br/>
&quot;FLAG&quot;: &quot;Yes&quot;<br/>
},</p>
<p>If</p>
<p class="Code">WD_List_Filter=Redact&gt;1</p>
<p>Email addresses are hidden with asterisks:</p>
<p class="Code">{<span style="font-family: &#39;Cambria Math&#39;, serif;">​​​​​​​​<br/>
</span>&quot;Rec&quot;:&quot;1&quot;,<br/>
&quot;L&quot;:&quot;2&quot;,<br/>
&quot;ADDR&quot;:&quot;(***) ***-**79&quot;,<br/>
&quot;ADDR.ASIS&quot;:&quot;+*********79&quot;,<br/>
&quot;ADDR.VIEW&quot;:&quot;(***) ***-**79&quot;,<br/>
&quot;NAME&quot;:&quot;John’s Cell&quot;,<br/>
&quot;FLAG&quot;:&quot;Yes&quot;<br/>
}<span style="font-family: &#39;Cambria Math&#39;, serif;">​​​​​​​​</span>,</p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h2><a id="JSON_Successful_2FGET_Response"></a>JSON Successful 2FGET 
 Response</h2>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">{</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;root&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;errorStatus&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_ID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;x211D3D8&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;List_Count&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;2&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ErrorCount&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCTX&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_MSG&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAL&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Error&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        },</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;data&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: [</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Rec&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;L&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;1&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ADDR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;(551) 655-5721&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ADDR.ASIS&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;+15516555721&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ADDR.VIEW&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;(551) 655-5721&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FLAG&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Yes&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            },</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Rec&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;2&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;L&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;2&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ADDR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;dsnyder@worldox.com&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ADDR.ASIS&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;dsnyder@worldox.com&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ADDR.VIEW&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;dsnyder@worldox.com&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FLAG&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;Yes&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        ]</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">}</span></p>
<p class="up_arrow"><span style="font-style: italic; font-weight: bold;"><i><b><a href="#"><img src="assets/images/up_arrow.gif" alt="up_arrow.gif" title="up_arrow.gif" style="border: none;" width="14" height="16" border="0"/></a></b></i></span></p>
<h2><a id="JSON_Failed_2FGET_Response"></a>JSON Failed 2FGET Response</h2>
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
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAL&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;pQG7rtsguFSwdhnaBLtpvrtxOwZoDI4bGO3EnXdTMRHy1bqg1FctD7A6Gw8$3Dkopkp[wy&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Error&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: [</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;8740&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_RCTX&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;WDRC_SID_INVALID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_MSG&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;WDRC_SID_INVALID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;wd_SID&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                    </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;wd_Error_VAL&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;pQG7rtsguFSwdhnaBLtpvrtxOwZoDI4bGO3EnXdTMRHy1bqg1FctD7A6Gw8$3Dkopkp[wy&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            ]</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        },</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;data&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: [</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            {</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;Rec&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:R#%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;L&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:L#%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ADDR&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:ADDR%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ADDR.ASIS&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:ADDR.ASIS%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;ADDR.VIEW&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:ADDR.VIEW%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;NAME&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:NAME%&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">,</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">                </span><span style="font-size: 9.0pt; font-family: Consolas; color: #A31515;">&quot;FLAG&quot;</span><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">: </span><span style="font-size: 9.0pt; font-family: Consolas; color: #0451A5;">&quot;%:FLAG%&quot;</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">            }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">        ]</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">    }</span></p>
<p style="margin: 0in; line-height: 13.5pt; background-color: #fffffe;"><span style="font-size: 9.0pt; font-family: Consolas; color: #000000;">}</span></p>
<p> </p>
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
