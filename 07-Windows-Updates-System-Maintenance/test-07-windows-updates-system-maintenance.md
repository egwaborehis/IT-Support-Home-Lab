# Test 07 — Windows Updates & System Maintenance

## Overview

For this test, I focused on Windows Updates and basic system maintenance.

I wanted to practise checking whether a computer was up to date, looking through previous updates and understanding the different types of updates Windows can install.

I also looked at driver updates and optional firmware updates. I did not install the optional updates because there was no problem on my computer that required them. Instead, I used the test to practise investigating them and deciding whether they were actually needed.

This is useful for IT support because checking Windows Update can be an important part of troubleshooting problems with Windows, hardware and security.

---

## Objectives

For this test, I wanted to:

- Check whether Windows was up to date.
- Perform a fresh update check.
- Look through my Windows Update history.
- Understand the different types of updates.
- Investigate my installed driver updates.
- Check for optional driver and firmware updates.
- Understand why optional updates should not always be installed.
- Practise using Windows Update as part of a troubleshooting process.

---

# 1. Checking My Windows Update Status

I started by opening:

**Settings → Windows Update**

Windows showed:

**"You're up to date"**

It also showed that the computer had been checked recently.

I noticed that there were two Microsoft Defender updates shown on the page, and both were marked as **Completed**.

These were:

- Security Intelligence Update for Microsoft Defender Antivirus
- Microsoft Defender Antivirus antimalware platform update

This showed me that my computer was receiving security-related updates as well as normal Windows updates.

### Evidence

[Windows Update status](windows-update-status.png)

This screenshot shows my Windows Update page reporting that the computer was up to date.

---

# 2. Understanding "You're Up to Date"

One thing I noticed during this test was that **"You're up to date" doesn't necessarily mean there are no updates anywhere on the computer**.

Later in the test, I found that Windows had some optional driver and firmware updates available.

This helped me understand that Windows separates normal required updates from optional updates.

From an IT support point of view, I think this is important because I shouldn't just see an optional update and immediately install it.

Instead, I would want to know:

- What does the update change?
- What device is it for?
- Is the user actually having a problem with that device?
- Is the update recommended for that problem?
- Could making the change introduce another issue?

---

# 3. Checking My Update History

Next, I opened:

**Settings → Windows Update → Update history**

This allowed me to see the updates that had previously been installed on my computer.

I found:

- **Quality Updates:** 8
- **Driver Updates:** 25
- **Definition Updates:** 13
- **Other Updates:** 2

The Quality Updates section contained several different security, critical and .NET Framework updates.

The updates I could see were marked as **successfully installed**.

### Evidence

[Windows Update history](windows-update-history.png)

This screenshot shows my Quality Update history and several updates that had been successfully installed.

---

# 4. Looking at the Different Update Categories

While looking through Update History, I saw that Windows separates updates into different categories.

### Quality Updates

Quality Updates are used to provide Windows fixes, improvements and security updates.

I found several of these in my own update history.

### Driver Updates

Driver Updates are related to the software that allows Windows to communicate with hardware.

For example, drivers can be used for things such as:

- Graphics
- Audio
- Wi-Fi
- Bluetooth
- Storage
- Other hardware devices

This is particularly useful to know for IT support because a driver problem could sometimes cause a hardware device to stop working properly.

### Definition Updates

Definition Updates are commonly associated with Microsoft Defender.

They provide updated security information that helps Defender recognise newer malware and other threats.

### Other Updates

The Other Updates category contains updates that don't fall into the main categories above.

---

# 5. Investigating My Driver Update History

I then expanded the **Driver Updates** section.

There were **25 driver updates** listed.

The updates I could see included components from:

- HP Inc.
- Lenovo Ltd.
- Realtek

Some of the visible updates included:

- HP Inc. Extension Driver Update
- Lenovo System Driver Update
- Lenovo Firmware
- Lenovo Extension
- Realtek Software Components

The updates shown in the screenshot were marked as **successfully installed**.

### Evidence

[Windows driver update history](windows-driver-update-history.png)

This screenshot shows my Driver Update history and several successfully installed driver updates.

---

# 6. Why Driver Updates Are Important

Looking through the driver history helped me understand why drivers can be important when troubleshooting hardware.

For example, if a user told me that their:

- Wi-Fi stopped working
- Bluetooth stopped working
- Speakers stopped working
- Display was behaving strangely
- Device was not being detected

I could consider whether a driver problem might be involved.

I would not immediately assume that the driver was the problem, though. I would first investigate the issue and identify the affected hardware.

I could then check Device Manager, Windows Update and the update history to see if there had been any recent changes.

---

# 7. Checking Optional Updates

I also checked the **Optional Updates** section.

Windows showed that there were **3 optional driver updates** available.

They were:

- Lenovo Ltd. — Firmware — 1.0.0.15
- Lenovo Ltd. — Firmware — 14.1.77.2497
- Lenovo Ltd. Firmware Driver Update — 1.38.0.0

### Evidence

[Windows optional driver updates](windows-optional-driver-updates.png)

This screenshot shows the three optional Lenovo driver/firmware updates available on my computer.

---

# 8. Why I Did Not Install the Optional Updates

I decided not to install these updates because my computer wasn't experiencing a problem that required them.

I wanted this test to be about **investigating and understanding updates**, rather than changing things unnecessarily.

The updates were optional, and some of them were firmware-related, so I didn't think it would make sense to install them just to create evidence for the lab.

This taught me that an IT support technician shouldn't make changes just because an update is available.

If I was helping a user with a specific hardware problem, I could investigate whether one of these updates was relevant before deciding whether to install it.

---

# 9. Performing a Fresh Update Check

After looking through the update history and optional updates, I returned to the main Windows Update page.

I clicked:

**Check for updates**

Windows completed the check and still reported:

**"You're up to date"**

This gave me a fresh confirmation that there were no required Windows updates waiting to be installed.

The optional driver and firmware updates were still listed separately.

---

# 10. How I Would Use This in IT Support

I can see how this process could be useful when dealing with a real help desk ticket.

For example, if a user told me:

> "My Wi-Fi has stopped working."

I wouldn't immediately start installing updates.

I would first ask some questions and investigate the problem.

I could then:

1. Check whether the user is connected to Wi-Fi.
2. Check whether other devices can connect.
3. Check the Wi-Fi adapter in Device Manager.
4. Check whether there are any device errors.
5. Check the current driver.
6. Check Windows Update.
7. Look at the Update History.
8. Check whether there are any relevant optional driver updates.
9. Decide whether a driver update is actually appropriate.
10. Test the Wi-Fi again after making any changes.

This gives me a more structured way of troubleshooting instead of just trying random fixes.

---

# 11. Safe Update Management

During this test, I made sure not to install or uninstall anything unnecessarily.

I think this is an important habit to develop for IT support.

Before making a change, I should understand:

- What I am changing.
- Why I am changing it.
- What problem I expect it to solve.
- Whether the change could cause another problem.
- How I will test the computer afterwards.

I also learned that firmware updates should be treated carefully because they can be more closely connected to the hardware than normal Windows updates.

---

# 12. What I Learned

This test helped me understand Windows Update in more detail.

I learned how to:

- Check whether Windows is up to date.
- Perform a fresh update check.
- View Windows Update history.
- Identify Quality Updates.
- Identify Driver Updates.
- Identify Definition Updates.
- Identify Other Updates.
- Investigate installed driver updates.
- Check for optional updates.
- Understand the difference between normal and optional updates.
- Understand why optional driver and firmware updates should not automatically be installed.
- Use Windows Update as part of a troubleshooting process.

One of the main things I took away from this test was that **checking for updates is not the same as blindly installing updates**.

I need to understand what an update is for and whether it is actually relevant to the problem I'm trying to solve.

---

# Skills Demonstrated

Through this test, I practised:

- Windows Update management
- Windows system maintenance
- Update history investigation
- Driver investigation
- Firmware update awareness
- Microsoft Defender update awareness
- Basic Windows troubleshooting
- System maintenance
- Safe change management
- IT support troubleshooting

---

# Evidence

I collected the following screenshots as evidence of the work I completed:

1. [Windows Update status](windows-update-status.png)
2. [Windows Update history](windows-update-history.png)
3. [Windows driver update history](windows-driver-update-history.png)
4. [Windows optional driver updates](windows-optional-driver-updates.png)

---

# Conclusion

For this test, I investigated Windows Update and looked at how updates are managed on my computer.

I started by checking the current update status and found that Windows reported that I was up to date. I then looked through my update history and found several successful Quality, Driver, Definition and Other updates.

I also investigated my driver update history and found updates from manufacturers such as HP, Lenovo and Realtek.

Finally, I checked the Optional Updates section and found three Lenovo firmware/driver updates. I decided not to install them because there was no specific problem on my computer that required them.

Overall, this test helped me understand that Windows Update can be more useful for IT support than simply clicking **Check for updates**. I can use the update history and driver information to help investigate problems and make more informed decisions about whether an update is actually needed.
