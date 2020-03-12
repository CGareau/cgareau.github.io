---
layout: post
title: Tool `4D_Info_Report`
permalink: /info_report_en/
categories: [PROCESS, SUPPORT]
tags: [info, report, component, 4D]
lang: en
lang-ref: info_report
---

![info_report](/images/info_report.png)

## About this component?
_(version 4.9rZF)_


The component `4D_Info_Report` provides a large number of information:

* about the operating system, the computer and the 4D Application

* on the database: description of the structure, data file, size, settings, etc.

* while the server is running, variation of memory, cache usage, connected users, processes, etc.

<br>

## How to use this component?

**_Procedure n°1:_**

Create a folder `Components` next to the structure or application file (if it does not already exist), copy the unarchived component, and restart your 4D or 4D Server.

Then you can directly execute the shared method: `aa4D_NP_Report_Manage_Display` from 4D Remote.

A dialog from the component will let you start the Stored procedure to create reports every N minutes on the Server.

You can also implement in your Host database, this small code in your `On Server startup` method to execute any of the shared methods (they all begins with `aa4D_`):

<pre>
  <code class="4d">
 ARRAY TEXT($at_Components;0)
 COMPONENT LIST($at_Components)
 If(Find in array($at_Components;`4D_Info_Report@`)>0)
  // to start the stored procedure creating report every 5 minutes
    EXECUTE METHOD(`aa4D_NP_Schedule_Reports_Server`;*;5;0)
 End if
   </code>
</pre>

**_Procedure n°2:_**

You can just create one report using the shared method `aa4D_NP_Util_CreateReport_Serv`.

The created reports (text files) are stored in a created folder `Folder_Reports` next to the data file.

<br>

In both cases, you should create a new shared method `aa4D_Host_GetDBParam` with the code below:

<pre>
  <code class="4d">
  // Method name: aa4D_Host_GetDBParam (must be shared with components)
 C_LONGINT($1) // selector
 C_REAL($0)
 $0:=-1 // Error, no parameter
 If(Count parameters>0)
    $0:=Get database parameter($1)
 End if
   </code>
</pre>

<br>

## How to analyze reports?

You can analyze these reports:

* from a remote 4D by executing the `aa4D_NP_Report_Manage_Display` method,

* from a single-user 4D by opening the component and clicking on the `File / Local reports compare` menu.

<br>

## Download

* reference of the component: 4D_Info_Report_v4_9_Ref_v28.pdf

* host database (v15) with some host shared methods example (please add the component in the `Components` folder for your test: 4D_Info_Report_Host_T_v7_v15.zip

* component for version 4D v18: 4D_Info_Report_v4_9rZF_v18.zip

* component for version 4D v17 (only compiled for 64-bit): 4D_Info_Report_v4_9rZF_64-bit_v17.zip

* component for version 4D v17 (also compiled for 64-bit): 4D_Info_Report_v4_9rZF_v17.zip

<br>

## Archives

* component for version 4D v16 (also compiled for 64-bit): 4D_Info_Report_v4_9rZC_rev1_v16.zip

* component for version 4D v15 (also compiled for 64-bit): 4D_Info_Report_v4_9rZ8_rev1_v15.zip

* component for version 4D v14 (also compiled for 64-bit): 4D_Info_Report_v4_9rZ2_v14_rev1.zip

* component for version 4D v13 (also compiled for 64-bit): 4D_Info_Report_v4_9rZ2_v13_rev1.zip

* component for version 4D v12 (also compiled for 64-bit): 4D_Info_Report_v4_9rZ_v12.zip

* host database (v12) with some host shared methods example (please add the component in the `Components` folder for your test: 4D_Info_Report_Host_T_v6_v12.zip