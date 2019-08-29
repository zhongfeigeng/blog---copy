---
title: Missing paragraph styles
---

When I open a document, my paragraph styles window is completely empty. There are no styles listed. There are no buttons at the bottom for new style, etc. How do I get this back? Thanks!
<!--more-->
correct answer: trash your ID preferences
Troubleshooting 101: Replace, or "trash" your InDesign preferences [2009 Outdated & Locked]
Peter Spier 2018-5-28 上午6:07When InDesign starts to behave strangely, the number one suggestion for troubleshooting is to replace (or trash, reset or restore) the application preferences. This will remove corrupt preferences and replace them with a new set of default preferences, and often end bad behavior.
 
There is a quick and easy method for doing this using the keyboard: close and relaunch InDesign, and IMMEDIATELY hold down Ctrl + Alt + Shift (Windows) or Cmd + Ctrl + Opt + Shift (Mac), and respond in the affirmative to the dialog asking if you really want to replace the preferences. There are two downsides to this method, however. First, you must be extremely fast on the keyboard (if you don’t see the confirmation prompt, you were too slow), and second, anytime you replace the preferences you will lose most program customizations, and using the keyboard method leaves you with no backup to restore them when the problem turns out to be something else.
 
My preferred method is to CLOSE INDESIGN and do a “manual” prefs replacement, which consists of finding and renaming the two files which make up the preference set: InDesign Defaults and InDesign SavedData. BOTH of these files should be replaced at the same time. You can delete them, but renaming or moving them will give you the opportunity to copy them back in the event that new prefs doesn’t cure your issue. When you restart ID, the program will look for these two files, and when they are not found, a new default set will be written.
 
[Defunct link removed by Peter Spier on 11/6/15]
 
These are normally hidden files, so you will need to set your system to show them. They will be found in various places depending on the OS, and the version of InDesign. (Edit: For Mac users running OSX 10.7 or newer, you can learn how to show hidden files here: Access hidden user library files | Mac OS 10.7 Lion)
 
PLEASE LOOK AT THESE PATHS CAREFULLY. They look similar, but are two different folders for the two files.
 
InDesign Defaults:
Windows XP: C:\Documents and Settings\<USER>\Application Data\Adobe\InDesign\<Version #>\<language>\  (Note: Prior to version 6 [CS4] the language folder is not used).
Windows Vista or Windows 7 and newer: C:\Users\<USER>\AppData\Roaming\Adobe\InDesign\<Version #>\<Language>\ (Note: Prior to version 6 [CS4] the language folder is not used).
Macintosh: Hard Drive/Users/<USER>/Library/Preferences/Adobe InDesign/<Version #>/<Language>/(Note: Prior to version 6 [CS4] the language folder is not used).
 
InDesign SavedData:
Windows XP: C:\Documents and Settings\<USER>\Local Settings\Application Data\Adobe\InDesign\<Version #>\<Language>\Caches\ (Note: Prior to version 6 [CS4] the language folder is not used).
Windows Vista or Windows 7 and newer: C:\Users\<USER>\AppData\Local\Adobe\InDesign\<Version #>\<Language>\Caches\  (Note: Prior to version 6 [CS4] the language folder is not used).
Macintosh: Hard Drive/Users/<USER>/Library/Caches/Adobe InDesign/<Version #>/<Language>/ (Note: Prior to version 6 [CS4] the language folder is not used).
 
In some earlier versions of ID, InDesign SavedData may also be found in the first directory.
 
 
As mentioned above, when you replace your preferences you will lose customizations beyond those things that are set in the preferences dialogs. These include Document and Print Presets you might have created. If you haven't made backups already, you should go, prior to replacing the preferences, to the "Define" dialogs for printer and document presets and custom stroke styles, and select all of your custom entries, the click the save button and put the file someplace safe. After resetting preferences using the keyboard or by renaming/deleting the old files and restarting InDesign, these customized settings can be re-loaded with a single click once again in the Define dialogs.     PDF presets can be backed up in the same way, but they are stored in a different location and will not be destroyed by a simple preference reset. Other customizations that you should not lose are workspaces, keyboard shortcut sets, and find/change queries.
 
As a further step I strongly recommend that you make a copy of these two files when you have a working customized set. Store them in a safe place and you can use them to overwrite a corrupt set so no further editing or reloading will be required. Users of InDesign CS4 can use a free script from InTools.com to backup and store multiple sets of preferences: In-Tools Scripts » Preference Manager Script
 
Edit: Corrected Mac Path per Jongware's post below.
 
UPDATE: I just ran across a situation in which overwriting the InDesign Defaults and InDesign SavedData files failed to restore functionality to the tools on a single user account on a multiple user system (the other account was fine). This is an absolute first and I've been using the technique for years, including replacing these two files on this system which is used by the student newspaper where I was a professor, in order to customize or restore preferences every semester. What did work was to use the keyboard method first, then close InDesign and manually replace the two files to restore the prefs to the proper settings.  -- Peter
 
Further update: We have had several reports now in the CC versions of InDesign where using the manual method has failed to solve problems that are normally fixed by replacing preferences. to the best of my knowledge, using the keyboard method has solved the problem for each of those users. -- Peter
