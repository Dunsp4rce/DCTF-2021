---
layout: post
title: "Powerpoint-programing"
author: "vishalananth"
tags: ['Misc']
---

A login page in powerpoint should be good enough, right?

**Files**
- [chall.ppsx]({{site.baseurl}}/assets/Powerpoint-programming/chall.ppsx)

## Solution

Open the file in Microsoft Powerpoint, we tried other tools like LibreOffice and WPS Office but it did not work. Rename the file from `chall.ppsx` which will open in Kiosk Mode to `chall.ppt` which will open it in the edit mode in Powerpoint. Go to the Animations Menu and you will see only a few buttons have animations associated. You will also find the animations trigger order on the right pane, you can see that animation will correspond to a button on the keyboard. Tracing it fully gives us the flag.

## Flag
```
DCTF{PPT_1SNT_V3RY_S3CUR3_1S_1T}
```
