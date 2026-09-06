# Test 08 — File Management, Backup & Recovery

## Overview

For this test, I focused on file management, basic backups and recovering deleted files.

I wanted to practise these areas using files that I created specifically for the lab rather than using any of my real personal or university documents. This meant I could safely simulate situations that could happen to a real user, such as accidentally deleting an important file.

I also explored the backup and recovery features built into Windows. This helped me understand the difference between recovering a recently deleted file and having a separate backup available if the original data is lost.

---

## Setting Up the Test

I started by creating a folder on my Desktop called:

`ITSupportLab-Test08`

Inside this folder, I created:

`Important-Files`

I then created three test files:

- `User-Notes.txt`
- `Support-Ticket.txt`
- `Backup-Test.txt`

I added simple text to each file so I could identify them and check their contents later.

I also created a folder called:

`Support-Documents`

I moved `Support-Ticket.txt` into this folder so I could practise organising files into a basic folder structure.

The structure looked like this:

ITSupportLab-Test08
└── Important-Files
    ├── User-Notes.txt
    ├── Backup-Test.txt
    └── Support-Documents
        └── Support-Ticket.txt

This gave me a small but realistic file structure to work with.

---

## File Organisation

Moving `Support-Ticket.txt` into its own folder gave me some basic practice with organising files.

Although this was a simple task, I can see how it could come up regularly in IT support. A user might think that a file has disappeared when it has actually been moved to another folder or saved somewhere they weren't expecting.

Being able to navigate folders, identify where files are stored and organise documents properly is therefore a basic skill that would be useful when helping users.

---

## Creating a Backup Copy

After organising the files, I created another folder inside `ITSupportLab-Test08` called:

`Backup`

I then copied the entire `Important-Files` folder into the new `Backup` folder.

This gave me a separate copy of the files while keeping the original files in their original location.

The structure became:

ITSupportLab-Test08
├── Important-Files
│   ├── User-Notes.txt
│   ├── Backup-Test.txt
│   └── Support-Documents
│       └── Support-Ticket.txt
│
└── Backup
    └── Important-Files
        ├── User-Notes.txt
        ├── Backup-Test.txt
        └── Support-Documents
            └── Support-Ticket.txt

I then checked the backup folder to make sure the files had copied correctly.

### Evidence

[Backup copy evidence](backup-copy-evidence.png)

This screenshot shows the separate backup copy of my test files.

The method I used here is a very basic form of backup because I manually copied the files into another folder. I understand that this is different from having a proper automated backup system, but it helped me understand the main idea of keeping another copy of important data.

In a real environment, backups could use external drives, network storage, cloud storage or dedicated backup software.

---

## Simulating an Accidental File Deletion

Once I had created a backup, I wanted to simulate a situation that could realistically happen to a user.

I went back to the original `Important-Files` folder and deleted:

`Backup-Test.txt`

I deliberately used one of my test files because I didn't want to risk deleting any real documents.

After deleting it, Windows moved the file to the Recycle Bin.

This created a simple support scenario where a user could say:

> "I've accidentally deleted an important file. Can you help me get it back?"

---

## Recovering the Deleted File

I opened the Windows Recycle Bin and found:

`Backup-Test.txt`

The file had not been permanently deleted, so I right-clicked it and selected **Restore**.

Windows returned the file to its original location inside:

`ITSupportLab-Test08 → Important-Files`

I then checked the folder and confirmed that `Backup-Test.txt` had returned.

I also opened the file to make sure that the contents were still there.

### Evidence

[File recovery using the Recycle Bin](file-recovery-recycle-bin.png)

This screenshot shows the test file back in the `Important-Files` folder after I recovered it.

This gave me practical experience with one of the simplest ways of recovering a recently deleted file.

---

## Recycle Bin vs Backup

One of the main things I learned from this test was that the Recycle Bin and a backup serve different purposes.

The Recycle Bin is useful when a user accidentally deletes a file and it is still available for restoration. However, I wouldn't treat the Recycle Bin as a proper backup system.

For example, if the Recycle Bin was emptied or the file was permanently deleted, I would need another way of recovering the data.

This is where the separate backup copy I created became useful.

I still had:

`Backup → Important-Files → Backup-Test.txt`

even after deleting the original file.

That meant I had another copy available if the original could not be recovered from the Recycle Bin.

### Evidence

[Backup copy evidence](backup-copy-evidence.png)

Having another copy of a file is much more useful if the original computer, drive or file becomes unavailable.

In a real environment, backups would normally be more advanced than the simple folder copy I used here. They could involve external drives, network storage, cloud storage or automated backup software.

---

## Looking at Windows Recovery Options

After practising file recovery, I explored the recovery options built into Windows.

I opened:

**Settings → System → Recovery**

The page showed several different recovery and troubleshooting options, including:

- Fix problems without resetting the PC
- Fix problems using Windows Update
- Reset this PC
- Advanced startup
- Quick machine recovery
- Point-in-time restore

### Evidence

[Windows recovery options](windows-recovery-options.png)

I found this useful because it showed me that Windows has several different levels of recovery.

For example, if a computer has a problem, I shouldn't immediately assume that resetting the entire PC is the correct solution. There are less disruptive troubleshooting and recovery options that can be considered first.

The recovery page also showed that some options are designed for more serious problems, such as startup issues.

I made sure not to select **Reset PC**, **Restart now** or any other option that could make a major change to my computer. I was only investigating the available options.

---

## Understanding Recovery vs Backup

Looking at the Windows recovery options helped me understand that backup, restore and recovery are related but different things.

A backup is mainly about keeping another copy of important data so that it can be recovered if something goes wrong.

Restoring means taking backed-up or previously saved data and bringing it back to where it is needed.

Recovery can involve fixing or returning the computer itself to an earlier working state.

For example, recovering a deleted text file from the Recycle Bin is different from using a Windows recovery option to deal with a serious operating system problem.

This distinction is useful for IT support because the correct solution depends on what has actually gone wrong.

---

## Checking Windows Backup

I also opened:

**Settings → Accounts → Windows Backup**

My computer showed that Windows Backup was already being used.

The page showed:

- Last backup: 3 September 2026
- OneDrive: Syncing
- App list: Backed up
- Preferences: Backed up
- Remember my apps: On
- Remember my preferences: On

### Evidence

[Windows Backup options](windows-backup-options.png)

This showed me that Windows Backup can cover more than simply copying individual documents.

The settings on my computer showed that OneDrive was syncing and that certain apps and preferences were being backed up.

This also gave me an example of how cloud-based backup and synchronisation can be used alongside other recovery methods.

---

## How I Would Handle a Real File-Loss Support Ticket

If a user contacted me and said that they had accidentally deleted an important document, I would first try to understand exactly what happened.

I wouldn't immediately start changing settings or using recovery tools.

I would check things such as:

- What was the name of the file?
- Where was it originally saved?
- When was it last seen?
- Was it accidentally deleted?
- Is it in the Recycle Bin?
- Was it stored in OneDrive or another cloud location?
- Is there a backup available?
- Is the file actually missing, or could it have been moved?

If the file was recently deleted and was still in the Recycle Bin, restoring it would be a straightforward first step.

After restoring it, I would open the file and make sure it was working correctly.

If it wasn't in the Recycle Bin, I would then look at other possible recovery options, such as a backup or cloud copy.

This is where having a backup becomes much more important.

---

## What I Would Do If the Computer Had a Larger Problem

The Windows Recovery page also showed me that file recovery isn't the only type of recovery an IT technician may need to deal with.

For example, if Windows itself was having serious problems, options such as troubleshooting, reinstalling Windows, Advanced Startup or other recovery tools could become relevant.

However, I would be careful about using these options because some recovery actions can have much bigger consequences than simply restoring a deleted file.

Before performing a major recovery action on a real user's computer, I would want to:

- Understand the exact problem.
- Check whether the user's important data is backed up.
- Identify the least disruptive solution.
- Explain what I am going to do.
- Make sure the user understands any possible data loss.
- Perform the recovery carefully.
- Test the computer afterwards.

This is important because solving one problem shouldn't create a bigger one.

---

## Safe Testing

I made sure that all of the practical work in this test was done using files that I created specifically for the lab.

I didn't use any important personal, university or work documents.

I also didn't reset my computer, reinstall Windows or restart into Advanced Startup because those actions weren't necessary for the test.

Instead, I focused on safely investigating the available options and using the test files to demonstrate actual file recovery.

This allowed me to get practical experience without putting my own important data at risk.

---

## What I Learned

This test gave me practical experience with several areas of file management and recovery.

I practised creating folders, moving files, organising documents and creating a separate copy of important files.

I then simulated an accidental deletion and successfully recovered the deleted file from the Recycle Bin.

I also checked the separate backup copy and saw how it provided another way of recovering the data.

Looking at Windows Recovery helped me understand that there are different recovery methods depending on how serious the problem is. I also explored Windows Backup and saw that my computer was already using OneDrive syncing along with app and preference backup.

The biggest thing I took away from this test is that **backup and recovery are not the same thing**.

The Recycle Bin was useful for recovering my recently deleted test file, but the separate backup gave me another copy of the data. If the file couldn't be recovered from the Recycle Bin, the backup could potentially be used instead.

---

# Skills Demonstrated

Through this practical test, I demonstrated experience with:

- Windows File Explorer
- File and folder organisation
- Creating folders
- Moving files
- Creating backup copies
- Basic data recovery
- Recycle Bin recovery
- Windows Backup
- OneDrive synchronisation awareness
- Windows Recovery options
- Understanding backup vs recovery
- Safe troubleshooting
- Data protection awareness
- Basic IT support investigation

---

# Evidence

The following screenshots provide evidence of the practical work I completed during this test:

1. [File recovery using the Recycle Bin](file-recovery-recycle-bin.png)
2. [Backup copy evidence](backup-copy-evidence.png)
3. [Windows recovery options](windows-recovery-options.png)
4. [Windows Backup options](windows-backup-options.png)

---

# Conclusion

For this test, I wanted to get some practical experience with file management, backups and recovery rather than just reading about them.

I created a set of test files, organised them into folders and made a separate backup copy. I then deliberately deleted one of the files and successfully recovered it using the Windows Recycle Bin.

After that, I checked the backup copy and explored the Windows Recovery and Windows Backup settings.

I found the difference between the Recycle Bin and a backup particularly useful. The Recycle Bin gave me a quick way to recover a recently deleted file, while the separate backup gave me another copy of the data that could be used if the original could not be recovered.

I also learned that Windows has several different recovery options, and the correct option depends on the problem. I wouldn't want to jump straight to something like resetting a PC without first understanding the problem and making sure important data is protected.

Overall, this test gave me useful hands-on experience with file management, basic backup practices and recovery, while also showing me how these skills could be applied to real IT support situations.
