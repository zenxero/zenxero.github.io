---
layout: post
title: "Windows Defender thinks non-existent files are a threat"
date: 2023-03-31 22:00:00 -0700
categories: windows
tags: windows defender security
---

# WTF Windows Defender?

While working on a batch/powershell script to automate the disabling of numerous of Windows settings, Windows Defender decided that the README for my script was a threat. This was obviously a false positive as it thought the README was a threat and not any of the actual powershell scripts. Anyways, I deleted the folder once I was done, but I didn't bother to select one of the action options I Defender. Little did I know that Defender would continue to alert me over the README "threat" that no longer existed on the filesystem.

Apparently, since I didn't "take action" from within the Defender control panel and deleted the file outside of it, Defender would keep alerting me over this "threat" forever. I tried to use the options that Defender provides like "Quarantine", "Remove", or "Allow", but nothing happened. LIKELY BECAUSE THE FILE NO LONGER EXISTS.

After some searching, I came across this post on the Microsoft Answers site.

[Threat found that can't be removed from a non existent file](https://answers.microsoft.com/en-us/windows/forum/all/threat-found-that-cant-be-removed-from-a-non/df404f7d-3d60-4688-8745-b578c3e1f3af)

This was exactly my problem, and it turns out that the solution is to navigate to this directory and delete everything in it.

```
C:\ProgramData\Microsoft\Windows Defender\Scans\History\Service\DetectionHistory
```

So I did that, rebooted my machine, and it worked!

Thanks to "JoseBeltre" on the Microsoft Answers site for the solution.
