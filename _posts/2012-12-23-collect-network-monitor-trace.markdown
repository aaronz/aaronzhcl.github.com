---
layout: post
status: publish
published: true
title: Collect Network Monitor Trace
author:
  display_name: aaronzh
  login: wdadmin
  email: webdebug.net@gmail.com
  url: ''
author_login: wdadmin
author_email: webdebug.net@gmail.com
wordpress_id: 14
wordpress_url: http://localhost:19634/?p=14
date: '2012-12-23 14:00:11 +0800'
date_gmt: '2012-12-23 14:00:11 +0800'
categories:
- IIS
- browser
- Data Collection
tags:
- IIS
- Network Monitor
- network
comments: []
---
<p>1. Download and install <strong>Network Monitor</strong> from <a href="http://www.microsoft.com/download/en/details.aspx?id=4865">http://www.microsoft.com/download/en/details.aspx?id=4865</a>.<br />
2. Open <strong>Network Monitor</strong> ans select <strong>File</strong> - <strong>New Capture</strong><br />
3. Click the <strong>Start</strong> button to start tracing.<br />
4. Reproduce the issue.<br />
5. Go back to <strong>Network Monitor</strong> and click <strong>Stop</strong>.<br />
6. Goto <strong>File</strong> - <strong>Save As</strong> and save the trace as a<strong> .cap</strong> file.<br />
7. Create a txt file and record ip addresses of <strong>client, server and proxy</strong> (if there is any).</p>
