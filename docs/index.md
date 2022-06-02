Worldox Web 3.x API Overview
============================

[Working with APIs](#working-with_APIs)

[API Requests](#api-requests)

Worldox Web is a web-based extension for the Worldox document management system. WD/Web Mobile provides authorized users with secure, controlled access to documents managed within the Worldox system over the Internet via standard browsers.

Worldox Web is a major upgrade to the original browser-capable Worldox/Web (v1.0). The entire user experience has been completely overhauled to provide a much more Worldox-like interface, and to make Worldox’s extensive document management capabilities easy to use in the web environment.

No plug-ins or additional software are required. For Administrators, there are significant enhancements to the underlying architecture in the original WD/Web Mobile Primary and document (proxy) server setup as well.

This guide describes Worldox Web’s APIs (Application Program Interfaces) or function calls that allow you to manipulate the Worldox interface or access its database directly.


## Working with APIs
-----------------

The APIs are low-level functions designed and built by programmers primarily for other programmers. They offer a great deal of control but generally forsake error control for compactness and efficiency. Therefore, error control and validation are left up to the programmer. It is critically important to employ generally accepted programming practices, such as variable initialization (beyond merely declaring variables) and checking function return codes before accepting values passed back in output variables.

It helps tremendously to know how Worldox works – from the Administrator’s perspective as well as from the end user’s. Please refer to the following:

See the Worldox GX4 Site Planning Guide for a complete discussion of how to set up and maintain Worldox. This document is available from the Worldox website in the Documentation section at [https://knowledgebase.worldox.com](https://knowledgebase.worldox.com "Worldox Knowledge Base").

See the Worldox Deployment Options and Security white paper available on the Knowledge Base. It describes Worldox Professional, Enterprise, Cloud and Web deployments.

You can also view helpful Worldox How-to-videos at: [http://www.worldox.com/howtovideos](http://www.worldox.com/howtovideos "Worldox How To Videos").

A few general notes about using the Worldox SDK:

You must initialize all variables before using them. This is particularly important for output variables that the functions use to return values.

Worldox does not save files. Use Worldox to determine the location to save the file to (based on the profile), then save the file programmatically as you would without Worldox.

If a Worldox API returns an error code, then you must assume that the value in the output variable is undefined.

Worldox is a user-centered program. The calls you make to Worldox will be subject to the same permissions, access, and settings as the local Worldox user.

You must destroy all lists when finished with them with the WDAPI\_DestroyList function.

Worldox is a dynamic environment with many users performing many tasks (saving, creating, editing, and so on) on many files – often simultaneously. Therefore, you cannot make assumptions about the “freshness” of data since it only affects tables and files. For details, see the WDAPI\_ReReadRecord function in the Worldox SDK Developer Guide v4.0. Please note that rereadrecord is used in the SERVE section of this guide.

### API Requests

Note that the following requests are used in the API:

-POST requests create new objects or send data to be handled

-GET requests retrieve data


