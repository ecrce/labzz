# labzz

Computer Forensics 7th Edition
Data Acquisition
Hands-On Project 4-1

In this project, you will familiarize yourself with the robocopy command and how to use the /s and /e switches to view the different results they produce. You will also use the /log: switch to record which files and folders are copied when robocopy is run from a PowerShell window.

You will also use the Get-ChildItem cmdlet to record a directory listing of files and subfolders in folders:

    Project_04-1_RoboCopy_Data,
    Project_04-1_RoboCopy_Data_S_switch, and
    Project_04-1_RoboCopy_Data_E_switch.

For the final step, you will use the cmdlets Compare-Object and Get-Content to compare the output of the two log files created by robocopy to see if the /s and /e switches produce different output values.

Complete the following steps:
Step 1

Connect to PLABWIN10 device, login, and navigate to the C:\Work\Data Files\ Mod04\Project_04-1 folder.

Open the file Project_04-1_Examiner_Notes.xlsx in your spreadsheet application. Type your name in the Examiner’s Name field and, in the Case Name and Case Number fields, type Project_04-1.

Practice Labs screenshot.
Step 2

Run PowerShell as administrator. You can find PowerShell by typing PowerShell in the Windows search box or by finding it in the application list. Right-click the PowerShell application and choose run as administrator.

Practice Labs screenshot.
Step 3

From the root directory, type cd “C:\Work\Data Files\Mod04\Project_04-1” and press Enter.

At the PowerShell prompt, type get-childitem and press Enter to view the contents of the Project_04-1 folder.

Practice Labs screenshot.
Step 4

At the PowerShell command prompt, type the following commands (one using the /s switch to create a folder containing no empty folders and one using the /e switch to create a folder that contains empty folders and hidden files) and press Enter after each one:

● robocopy Project_04-1_RoboCopy_Data Project_04-1_RoboCopy_Data_S-switch /s /log:Project_04-1_0_RoboCopy-with-S-switch.log

● robocopy Project_04-1_RoboCopy_Data Project_04-1_RoboCopy_Data_E-switch /e /log:Project_04-1_0_RoboCopy-with-E-switch.log

Copying the commands above from the text for execution in PowerShell may be problematic; you may miss spaces, etc. Refer to the image below so you get the command, spacing, etc., correct.

The image below shows PowerShell in full-screen mode. This is so commands don’t wrap to the next line, making it easier for you to view and confirm the syntax.

Practice Labs screenshot.
Step 5

Type the following commands (one to create a list that contains all files, including empty folders and hidden files, and one that only lists hidden files), and press Enter after each one:

    get-childitem -path Project_04-1_RoboCopy_Data -recurse -force > Project_04-1_1_Get_ChildItem_Force.txt
    get-childitem -path Project_04-1_RoboCopy_Data -recurse -hidden > Project_04-1_1_Get_ChildItem_Hidden.txt

Practice Labs screenshot.
Step 6

To create a list that contains all the files, including empty folders and hidden files, as well as a list that only includes hidden files for folder Project_04-1_RoboCopy_Data_S-switch, type the following two commands and press Enter after each one:

    get-childitem -path Project_04-1_RoboCopy_Data_S-switch -recurse -force > Project_04-1_2_Get_ChildItem_Force_S-switch.txt

    get-childitem -path Project_04-1_RoboCopy_Data_S-switch -recurse -hidden > Project_04-1_2_Get_ChildItem_Hidden_S-switch.txt

Practice Labs screenshot.
Step 7

To create a list that contains all files, including empty folders and hidden files, as well as a list that only includes hidden files for folder Project_04-1_RoboCopy_Data_E-switch, type the following commands and press Enter after each one:

● get-childitem -path Project_04-1_RoboCopy_Data_E-switch -recurse -force > Project_04-1_3_Get_ChildItem_Force_E-switch.txt

● get-childitem -path Project_04-1_RoboCopy_Data_E-switch -recurse -hidden > Project_04-1_3_Get_ChildItem_Hidden_E-switch.txt

Practice Labs screenshot.
Step 8

To complete this task, compare the two log files created by robocopy to see if they are different. In PowerShell, type the following command:

    compare-object (get-Content Project_04-1_0_RoboCopy-with-S-switch.log) (get-content Project_04-1_0_RoboCopy-with-E-switch.log) > Project_04-1_4_Logfiles_compare.txt

Practice Labs screenshot.

Practice Labs screenshot.

You can open the Project_04-1_4_Logfiles_compare.txt using Notepad to view its content.
Step 9

In the file Project_04-1_Examiner_Notes.xlsx, list the cmdlets that were used in this project.
Step 10

In the file Project_04-1_Examiner_Notes.xlsx, make notes about the differences between the files in each of the following pairs of files:

Compare the contents of the files:

    Project_04-1_0_RoboCopy-with-E-switch.log
    Project_04-1_0_RoboCopy-with-S-switch.log

Compare the contents of the files:

    Project_04-1_1_Get_ChildItem_Force.txt
    Project_04-1_1_Get_ChildItem_Hidden.txt

Compare the contents of the files:

    Project_04-1_2_Get_ChildItem_Force_S-switch.txt
    Project_04-1_3_Get_ChildItem_Force_E-switch.txt

Compare the contents of the files:

    Project_04-1_2_Get_ChildItem_Hidden_S-switch.txt
    Project_04-1_3_Get_ChildItem_Hidden_E-switch.txt

Step 11

In the file Project_04-1_Examiner_Notes.xlsx, make notes about the contents of the file Project_04-1_4_Logfiles_compare.txt.
Step 12

When you are finished, save your examiner notes and exit PowerShell. Submit to your instructor the following files:

    Project_04-1_Examiner_Notes.xlsx
    Project_04-1_0_RoboCopy-with-E-switch.log
    Project_04-1_0_RoboCopy-with-S-switch.log
    Project_04-1_1_Get_ChildItem_Force.txt
    Project_04-1_1_Get_ChildItem_Hidden.txt
    Project_04-1_2_Get_ChildItem_Force_S-switch.txt
    Project_04-1_2_Get_ChildItem_Hidden_S-switch.txt
    Project_04-1_3_Get_ChildItem_Force_E-switch.txt
    Project_04-1_3_Get_ChildItem_Hidden_E-switch.txt
    Project_04-1_4_Logfiles_compare.txt

Alert: When Internet Explorer or Edge is opened on a lab device you will be taken to http :// intranet, where you will be able to upload files within the lab environment.
To download files, use the following for guidance:
File manager access | ACI Learning Help Center
There are no screenshot items for this exercise.
Lab Assessment
Did you complete all the lab steps? Don't forget to complete the review questions on the next page.
