---
layout: post
status: publish
published: true
title: Troubleshoot Assembly Loading Failures
author:
  display_name: aaronzh
  login: wdadmin
  email: webdebug.net@gmail.com
  url: ''
author_login: wdadmin
author_email: webdebug.net@gmail.com
wordpress_id: 182
wordpress_url: http://www.webdebug.net:80/?p=182
date: '2013-01-13 14:12:17 +0800'
date_gmt: '2013-01-13 14:12:17 +0800'
categories:
- ASP.NET
- Troubleshooting
tags:
- assembly loading failure
- fusion log
- binding
- TypeLoadException
comments: []
---
<p>The <a href="http://msdn.microsoft.com/en-us/library/e74a18c4%28VS.71%29.aspx" target="_blank">Assembly Binding Log Viewer</a> displays details for failed assembly binds. This information helps you diagnose why the .NET Framework cannot locate an assembly at run time. These failures are usually the result of an assembly deployed to the wrong location or a mismatch in version numbers or cultures. The common language runtime's failure to locate an assembly typically shows up as a <a href="http://msdn.microsoft.com/en-us/library/system.typeloadexception(v=vs.71).aspx" target="_blank">TypeLoadException</a> in your application.</p>
<!--more-->
<p><strong><a href="http://blogs.msdn.com/b/suzcook/archive/2003/05/29/57120.aspx" target="_blank">Debugging Assembly Loading Failures</a></strong><br />
By Suzanne Cook<br />
So...you're seeing a FileNotFoundException, FileLoadException, BadImageFormatException or you suspect an assembly loading failure? Try the steps below to start your debugging process.<br />
First, get the Message property from the exception. If the exception's InnerException property is set, get the Message property from that. If the message is generic, also get the hresult by calling System.Runtime.InteropServices.Marshal.GetHRForException(), passing in the Exception object. If that info is not readily available, you may need to attach a debugger and set it to catch managed exceptions. Then, get the hresult by retrieving the private _HResult field of the managed Exception object.</p>
<p><strong><a href="http://blogs.msdn.com/b/junfeng/archive/2004/02/14/72912.aspx" target="_blank">Fusion binding log and fuslogvw.exe</a></strong><br />
By Junfeng Zhang</p>
<p>Suzanne blogs again! This time, she is helping you on diagnose MissingMethodException.<br />
Of course, whatever she tries to help you, she can't live without fusion log.<br />
So what exactly is fusion log?<br />
Remember what fusion's role is in assembly binding? Fusion is responsible for finding the actual bits, and handing it over to loader. Because the fusion probing rule is vastly different from normal LoadLibrary rule, fusion includes some logging information to help diagnostic assembly binding failures. For every major event, fusion will log a message. Those events include app.config lookup, policy resolution, GAC lookup, every location fusion probes, and more.</p>
