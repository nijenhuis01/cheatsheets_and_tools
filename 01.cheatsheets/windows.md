## WIndows Cheatsheet

|command|Description|
|---|---|
|xfreerdp /v:<target IP address> /u:htb-student /p:<password>|RDP to lab target|
|Get-WmiObject -Class win32_OperatingSystem|Get information about the operating system|
|dir c:\ /a|View all files and directories in the c:\ root directory|
|tree <directory>|Graphically displaying the directory structure of a path|
|tree c:\ /f | more|Walk through results of the tree command page by page|
|icacls <directory>|View the permissions set on a directory|
|icacls c:\users /grant joe:f|Grant a user full permissions to a directory|
|icacls c:\users /remove joe|Remove a users' permissions on a directory|
|Get-Service|PowerShell cmdlet to view running services|
|help <command>|Display the help menu for a specific command|
|get-alias	List|PowerShell aliases|
|New-Alias -Name "Show-Files" Get-ChildItem|Create a new PowerShell alias|
|Get-Module | select Name,ExportedCommands | fl|View imported PowerShell modules and their associated commands|
|Get-ExecutionPolicy -List|View the PowerShell execution policy|
|Set-ExecutionPolicy Bypass -Scope Process|Set the PowerShell execution policy to bypass for the current session|
|wmic os list brief|Get information about the operating system with wmic|
|Invoke-WmiMethod|Call methods of WMI objects|
|whoami /user|View the current users' SID|
|reg query <key>|View information about a registry key|
|Get-MpComputerStatus|Check which Defender protection settings are enabled|
|sconfig	Load Server|Configuration menu in Windows Server Core|

### General Commands
|command|Description|
|---|---|
|help <command>|Provides help information for Windows commands|
|Get-Help <cmdlet>|Displays help about Windows PowerShell cmdlets and concepts|
|Update-Help|Downloads and installs the most up-to-date help files for Windows PowerShell|
|CTRL-C|Interrupts a currently running process|
|Get-Module|View the modules loaded into your PowerShell session|
|Import-Module|Import a module into your PowerShell session|
|Get-Command|View all commands, cmdlets, functions, and aliases loaded into your PowerShell session|
|Set-Location <path>|Changes our location in the filesystem. Same as using CD|
|Get-Content <file>|View the contents of an object. Similar to type or cat|
|systeminfo|Displays operating system configuration information for a local or remote machine|
|hostname|Displays the name of the current host|
|ver|Displays the current Windows version|

### Terminal History
|command|Description|
|---|---|
|doskey /history|Prints out the session's command history to the terminal or output it to a file when specified|
|page up|Places the first command in our session history to the prompt|
|page down|Places the last command in history to the prompt|
|⇧|Scrolls up through our command history to view previously run commands|
|⇩|Scrolls down to our most recent commands run|
|⇨|Types the previous command to prompt one character at a time|
|F3|Retypes the entire previous entry to our prompt|
|F5|Pressing F5 multiple times allows us to cycle through previous commands|
|F7|Opens an interactive list of previous commands|
|F9|Enters a command to our prompt based on the number specified. The number corresponds to the command's place in our history|

### File & Directory Commands
|command|Description|
|---|---|
|dir|Lists directory contents|
|dir /A <attributes>|List directory contents with the specified attributes|
|dir /A:H|List hidden files in the current directory|
|dir /A:R|List read-only files in the current directory|
|cd|Prints current working directory|
|chdir|Prints current working directory. Alternate command|
|cd <path>|Changes the directory|
|chdir <path>|Changes the directory. Alternate command|
|tree <path>|Graphically displays the directory structure from the specified path|
|tree /F <path>|Graphically displays the directory structure from the specified path, including files within the directory|
|cls|Clears the terminal|
|mkdir <directory name>|Creates a directory in the current working directory(or specified directory) with the specified name|
|md <directory name>|Creates a directory in the current working directory(or specified directory) with the specified name. Alias of mkdir|
|rmdir <directory name>|Removes a directory in the current working directory(or specified directory) with the specified name|
|rmdir /S <directory name>|Recursively removes all directories and files in the specified directory|
|move [source] [destination]|Move file(s) from the source folder to the destination folder|
|copy [source] [destination]|Copy file(s) from the source folder to the destination folder. Only works with files and not folders|
|xcopy [source] [destination]|Copy file(s) and folder(s) from the source folder to the destination folder. Replaced by Robocopy and currently deprecated|
|xcopy /E [source] [destination]|Copy file(s) and folder(s) from the source folder to the destination folder, including empty directories|
|robocopy [source] [destination]|Copy files(s) and folder(s) from the source folder to the destination folder. It has a more robust feature set compared to xcopy|
|more <file>|Displays the output of a file or command one screen at a time|
|more /S <file>|Displays the output of a file or command one screen at a time. Compresses multiple blank lines into a single line|
|type <file>|Displays the contents of a file|
|fsutil file createNew <filename> <length>|Creates a new file with a specified file name and length|
|echo "example string" > <filename>|Writes the contents provided into a new or existing file with the specified filename. If the file does not exist, a new one will be created; otherwise, the previous file's contents will be overwritten|
|echo "example string" >> <filename>|Appends the provided contents to an existing file|
|ren <filename1> <filename2>|Renames a file|
|del <file>|Deletes a file or files|
|del /A:R <file>|Deletes a file or files with the read-only attribute set|
|del /A:H <file>|Deletes a file or files with the hidden attribute set|

###PowerShell
|command|Alias|Description|
|---|---|
|Get-Item|gi|Retrieve an object (could be a file, folder, registry object, etc.)|
|Get-ChildItem|ls / dir / gci|Lists out the content of a folder or registry hive|
|New-Item|md / mkdir / ni|Create new objects. ( can be files, folders, symlinks, registry entries and more)|
|new-item -name "Name" -ItemType <directory/file>|Specify the new items name and object type||	
|Set-Item|si|Modify the property values of an object|
|Copy-Item|copy / cp / ci|Make a duplicate of the item|
|Rename-Item|ren / rni|Changes the object name|
|Rename-Item .\Object-1.md -NewName Object-2.md|Rename object-1 to object-2||
|Remove-Item|rm / del / rmdir|Deletes the object|
|Get-Content|cat / type|Displays the content within a file or object|
|Add-Content <file> "Content to add"|ac|Append content to a file|
|Set-Content|sc|overwrite any content in a file with new data|
|Clear-Content|clc|Clear the content of the files without deleting the file itself|
|Compare-Object|diff / compare|Compare two or more objects against each other. This includes the object itself and the content within|