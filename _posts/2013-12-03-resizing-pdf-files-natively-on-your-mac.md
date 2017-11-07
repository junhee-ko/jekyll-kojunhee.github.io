---
id: 1747
title: Resizing PDF files natively on your Mac
author: colinmcnamara
excerpt: The challenge is, that I use LOTS of images and graphs in my presentations. This results in 50+ Megabyte files that are impossible to send via email. Resizing these down to a manageable size is not something that is natively available within OSX
layout: post
guid: http://www.colinmcnamara.com/?p=1747
permalink: /resizing-pdf-files-natively-on-your-mac/
categories:
  - Mac
tags:
  - mac
  - osx
  - preview
---
I have a headache that I face almost every day on my Mac. When I share a presentation externally, I can&#8217;t always share the native PPT. I have to distill out a PDF, and I use the native print utility within Mac OSX to creature the pdf.

The challenge is, that I use LOTS of images and graphs in my presentations. This results in 50+ Megabyte files that are impossible to send via email. Resizing these down to a manageable size is not something that is natively available within OSX.

### Solution to compressing PDF files natively with OSX

The solution is using quartz filters, and creating an Automator script to create an &#8220;application&#8221; that you use to compress your files. Below is the procedure to create this on your mac

1. download these set of Quartz filters to your laptop &#8211; <https://github.com/joshcarr/Apple-Quartz-Filters>

<img style="display: block; margin-left: auto; margin-right: auto;" title="joshcarr_Apple-Quartz-Filters.png" alt="Joshcarr Apple Quartz Filters" src="http://www.colinmcnamara.com/wp-content/uploads/2013/12/joshcarr_Apple-Quartz-Filters.png" width="500" height="324" border="0" />

2. Unzip the output and copy the qfilter files to your ~/Library folder

<img style="display: block; margin-left: auto; margin-right: auto;" title="qfilter.png" alt="qfilter" src="http://www.colinmcnamara.com/wp-content/uploads/2013/12/qfilter.png" width="500" height="231" border="0" />

3. Open Automater, choose **CREATE APPLICATION, **select **Apply Quarts Filter to PDF document ** and **Drag to the right window**. then **Choose the DPI from the drop down** and **Save as Application**

<img style="display: block; margin-left: auto; margin-right: auto;" title="automater-qfilter.png" alt="automater-qfilter" src="http://www.colinmcnamara.com/wp-content/uploads/2013/12/automater-qfilter.png" width="500" height="436" border="0" />

4. Save as an application (.App) and then drag the PDF you want to resize over that App file. In a couple seconds your PDF will be shrunk and available on your desktop.