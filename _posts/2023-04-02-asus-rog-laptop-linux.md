---
layout: post
title: "Asus ROG Gaming Laptop with Linux"
date: 2023-04-02 14:00:00 -0700
categories: linux
tags: linux fedora asus gaming
---

# Better than I expected.

A while back, I bought an Asus ROG Zephyrus G15 GA503QR (2021) gaming laptop. I had never intended to install Linux on it since Windows gaming laptops have historically not been very reliable Linux systems. Mostly due to issues surrounding proprietary drivers for audio, Wi-Fi, and the worst one... switchable NVIDIA graphics. This laptop has an AMD Ryzen 9 5900HS CPU/APU, an NVIDIA 3070 Laptop GPU, 16GB of RAM, and a 1440p 165Hz screen. Quite nice specs for an ~$1,800 USD laptop from Best Buy. My only real complaints are the fan noise when under load and the fact that the PCIe NVME is only version 3.0 instead of 4.0. And that's the limitation of the onboard PCIe, not the drive itself. So I'm not getting the full bandwidth from the storage that I could be.

Under Windows 10, everything works fine. But, in order to get the switchable graphics running, customize the battery charge level, adjust the fan curves, adjust the keyboard LEDs (because of course the keyboard has RGB), and some other things, you need to install various Asus programs that I would classify as bloatware. Even on a clean Windows 10 install (which has its own built-in bloat), you'll need a couple of drivers like the "Refresh Rate Service", the "MyAsus" app, and the "Asus Armory Crate" control center app. The MyAsus app is extremely useless to me and seems to mostly contain ads and offers for various unwanted software like Mcafee antivirus. The only reason to use it is to set the battery charge level. Yes, for some reason, they put that feature in this adware app. As for the Armory Crate app, that one is also bloated with unnecessary features. But, it's needed in order to automatically switch the power profile when you plug in the power brick, set the fan curves, adjust the keyboard RGB, etc. These apps always run in the background, spawn dozens of processes and services, and absolutely call home back to the Asus mothership.

For Windows 11, it's the same story. You need the MyAsus app, the Armory Crate app, and one or two extra drivers from the Asus site. But, with my increasing dissatisfaction with Windows 11 in particular I decided to try out Linux on the laptop, knowing that it would likely be a disaster of incompatibility and jank, probably because of the switchable graphics.

Well, after some searching I was extremely surprised to find out that there is an entire project devoted to making Linux work well on the Asus ROG laptops specifically.

[asus-linux.org](https://asus-linux.org/)

This project is awesome and they've created multiple utilities and packages that implement the functionality of the MyAsus and Armory Crate apps, but under Linux. They have several guides focusing on Fedora, Arch, and OpenSUSE. I chose Fedora KDE for my install base, then followed their guide to configure the package repos, install `asusctl`, the "ROG GUI", and `supergfxctl`.

To my surprise, it actually works! The ROG GUI lets you adjust all of the hardware settings like battery charge level, keyboard LEDs, fan curves, power notifications, POST sound, etc. The only downsides are that in order to change the switchable graphics configuration from Integrated to Hybrid, you need to logout and log back in. And since the laptop has NVIDIA graphics, you'll need to run under X11 instead of Wayland for stuff to work correctly. I don't really care about that, but that may be an issue for some.

I've been running this install on the G15 for several months now and it's been pretty solid. There are still issues with game compatibility obviously, but with Valve's Proton layer and all the work they've done for the Steam Deck, a lot of games will work no problem. But I also don't play online or competitive games that require anti-cheat and DRM, so it's generally much easier to get games to work that don't have those requirements. I'm also lucky in that I don't need to use any proprietary software that won't run under Linux like the various Adobe apps, MS Office, or anything like that for my personal use. Overall, it's worked out much better than I initially expected.