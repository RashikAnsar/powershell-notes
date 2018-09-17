## <center>Overview
### Comment
```powershell
# Single line comments
echo ""
<#
Multi-line
comments
in powershell
#>
```

>The Basic syntax of powershell commands is __Verd-Noun__.<br/> 

```powershell
#To get help for any cmdlet in powershell 
Get-Help Cmdlet

# To show all the commands in a sepeare window
Show-Command

# To get all the commands in console
Get-Command
```

### Cmdlet examples
```powershell
echo "Hi, How are you?" #This is a Print statement

Write-Output "Just like 'echo'" #To on to the console
Write-Host "Just like 'echo' and 'Write-Output'" #To on to the console

Clear-Host #To clear the console or `ctrl + L`

Get-Location #gives present working directory path

Set-Location C:\Learnings\Powershell #Change directory
Set-Location .. #Go back one directory

Get-Date #To get the current date

Get-ChildItem #To get all files and folder in the current working directory

Get-ChildItem -Path .\Learnings #To get all the items from specified path

#Copy a file from one location to another 
Copy-Item -Path .\readme.txt -Destination D:\PoShPractices\ 

#Copy everything from source to destination
#If you dont want to copy the files from sub-folder then remove `-Recurse` flag
Copy-Item -Path Powershell\* -Destination Practices\ -Recurse


#Move a file from one location to another 
Move-Item -Path .\readme.txt -Destination D:\PoShPractices\ 

#Move and rename
Move-Item -Path Powershell\readme.txt -Destination Practices\PSnotes.txt 

#Rename file or folder
#If you're giving space in between the words then "Quotation marks" 
Rename-Item -Path .\readme.txt -NewName PSnotes.txt

#Delete a file or folder
Remove-Item -Path .\readme.txt 
Remove-Item -Path .\Learnings -Recurse

# To get the list of different commands executed in shell
Get-History 

# To clear the history of commands executed in shell
Clear-History
```