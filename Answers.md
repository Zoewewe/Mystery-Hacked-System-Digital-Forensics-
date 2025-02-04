# Answers
Answers for Ali Hadi's Challenge #3 - Mystery Hacked System

## How was this system hacked? (What is your hypothesis)
1) Attacker delete magnify.exe
2) Copied cmd.exe
3) Changed the name of cmd.exe to magnify.exe
4) In the lock page, did cntl+ to activate cmd.exe

## What evidence did you find that proves your hypothesis?
1) Deleted magnify.exe on the day of the attack
2) When putting the new magnify.exe into virus total, it shows that program is actually cmd.exe

## How did you approach and solve the case? (write a report)

Tools:
Autopsy, ShellBags Explorer, Registry Explorer

Steps:
1) Open the 001 file in autopsy and extract SAM file
2) Analyse SAM file in Registry Explorer and go to Domain\Account\Users
	1) We can see that the only accounts logged in were Administrator and Master
3) Go to autopsy and extract USrClass.DAT from Administrator
4) Analyse file in ShellBags Explorer
	1) We can see 3 folders of importance, Tools, New Folder and Docs
5) Go to autopsy and analyse these folders
	1) We can find txt files in Tools and Docs
6) In autopsy, open deleted files and filter by Change Time
	1) magnify.exe is there
7) In autopsy, go to C:\Windows\System32 and extract magnify.exe
8) Put the extracted file into cmd.exe

## Anything you would like to add?
#### How they modified magnify.exe into cmd.exe
1) Use a windows repair USB and install a driver (This gives you a file manager, so you can access system32)
2) Delete the orginal magnify.exe and change the CMD.exe file to magnify.exe
3) From the windows login screen run the magnify accessibility shortcut (This gives you a system32 level command prompt)
