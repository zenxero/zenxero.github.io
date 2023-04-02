---
layout: post
title: "Fedora - Failed to set new EFI boot target"
date: 2023-03-31 23:00:00 -0700
categories: linux
tags: linux fedora uefi
---

# Too many dumps.

Recently, during a fresh Fedora Linux install on my laptop, I encountered an interesting error that I've never seen before. The installer would get stuck and fail with this error:

"Failed to set new efi boot target. This is most likely a kernel or firmware bug."

What? I've done multiple Linux and Windows installs on this laptop before, and I've never seen this. Well, it seems I'm not the only one who's encountered this error. Apparently, the EFI of the machine can get filled up with excess "dump" files. The solution is to delete them from a Linux live boot media.

```bash
rm /sys/firmware/efi/efivars/dump-*
```

Thanks to "aswyg" on the Fedora discussion forum for the solution.

[Bootloader installation has failed](https://discussion.fedoraproject.org/t/bootloader-installation-has-failed-failed-to-set-new-efi-boot-target-this-is-most-likely-a-kernel-or-firmware-bug/75630/6)

[I can't install Linux distros anymore](https://www.reddit.com/r/linuxquestions/comments/oyo7fe/i_cant_install_linux_distros_any_more/)
