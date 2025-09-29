---
title: "A Friday Lunch Fix: How I Broke My Omarchy Laptop Screen (and Repaired It in Emergency Shell)"
description: "A funny Linux troubleshooting story: disabling my laptop screen in Hyprland, breaking it during a remote lunch, and learning how to recover with cryptsetup and vi."
image: "me-at-coding.jpg"
slug: "a-friday-lunch-fix"
date: 2025-09-25T22:30:00Z
draft: false
tags: ["linux", "hyprland", "omarchy", "hardware", "troubleshooting", "anecdotes", "devlife"]
categories: ["anecdotes"]
---

{{< figure src="me-at-coding.jpg" alt="Working through laptop repairs at a cafe" >}}

Last week I planned a small coworking session with friends at a restaurant.  
I run **Omarchy** on my laptop (with Hyprland), and at home I usually work only with my external monitor.  
So, in my infinite wisdom, I disabled the laptop screen in `~/.config/hyprland/monitors.conf`.  
At home it looked like a *great fucking idea*.  

---

### ☕ The setup
At the restaurant, life was good. I had a latte, then a flat white, and even ordered a slice of carrot cake (highly recommended).  
Then I opened my laptop to start working.  

The screen stayed black.  

No problem, I thought. *I’ll just rent a monitor.*  
Five minutes later: no luck, the shop said no.  

So I tried Google, ChatGPT, random searches — nothing worked. I was about to give up and just watch my friends type on their glowing screens when one of them said:  
> “Can I try?”

---

### 🖥️ The emergency shell
In five minutes he had managed to enter the **emergency shell** (just by smashing `Ctrl+C` during boot).  
From there, I finally had hope.  

Here’s what we did, step by step:

* Decrypted the disk with `cryptsetup` (because my home partition is encrypted).  
* Mounted the disk and found the Hyprland config.  
* Edited the file (no `nano`, but luckily `vi` was available).  
* Removed the line that disabled the laptop monitor.  
* Saved, rebooted… and it worked.  

It felt like being back in college, fighting with Wi-Fi drivers for hours — frustrating but oddly fun.  

---

### 🍲 Happy ending
After fixing the issue, I shut down the laptop, enjoyed the rest of the remote day, and ended up at a vegetarian buffet with friends.  
A chaotic afternoon turned into a pretty good story (and a learning session).  

---

### 💡 Thoughts / Lessons
* Learned how to access the emergency shell (`Ctrl+C` during boot).  
* Confirmed that `cryptsetup` is the tool for decrypting LUKS partitions.  
* Emergency shell doesn’t have all your usual tools, but `vi` is almost always there.  
* Linux troubleshooting is always *try → fail → learn*. It’s frustrating, but that’s how you grow.  
* And of course: *“If it doesn’t work, you forgot to compile the kernel.”* (old Linux joke).  

---

## 🛠️ Technical Notes: Editing a Config in Emergency Shell

```sh
# Check partitions
cat /proc/partitions

# Example: open encrypted device
cryptsetup luksOpen /dev/nvme0n1p3 cryptroot
# (enter passphrase)

# Mount the device
mount /dev/mapper/cryptroot /mnt

# Navigate and edit the config
vi /mnt/home/<your-user>/.config/hypr/monitors.conf

# Remove the line disabling the monitor, e.g.:
# monitor=eDP-1,disable

# Save and reboot


``` 
---
