## Application
* An application is a program which you interact with on the desktop. This is what you spend almost all of your time using on the computer. Internet explorer, microsoft word, iTunes, skype - they are all applications.

## Process
* A process is an instance of a particular executable (.exe program file) running.
* A given application may have several processes running simultaneously.
* For example, some modern browsers such as google chrome run several processes at once, with each tab actually being a separate instance/process of the same executable.
* In some cases, complicated applications may have multiple processes; for example, Visual Studio runs a separate process when it compiles code from when it displays the IDE.
* However, most often, a given application is running from a single process; for example, no matter how many microsoft word windows you have open, only a single instance of winword.exe is running.

```powershell
# To get all the processes runnning 
Get-Process

# Get-Process cmdlet returnig value type
(Get-Process).GetType()

# Soring the process based on Process id in ascending order
Get-Process | Sort-Object id
# Select first 10 proccess of the sorted process list based on id
Get-Process | Sort-Object id | Select-Object -First 10 

# Soring the process based on cpu time in descending order and select highest 10
Get-Process | Sort-Object CPU -Descending | Select-Object -First 10

# Get a process with the help of its name
Get-Process -Name "powershell*"
Get-Process -Name "powershell*" | select *

# Get processes where cpu time is more than 50
# $_ which specifies the current object
Get-Process | Where-Object { $_.CPU -gt 50 }

# save the list obtained to a file
# file will be generated in the current working directory
Get-Process | Where-Object { $_.CPU -gt 50 } | Out-File maxCpuProcesses.txt

# kill a process
Get-Process -Name "powershell*" | Stop-Process
```

## Service
* A service is a process which runs in the background and does not interact with the desktop.
* In Windows, services almost always run as an instance of the svchost.exe process, the windows service host process; however there are sometimes exceptions to this.
```powershell
# To get all the services(running, stopped) 
Get-Service

# Get-Service cmdlet returnig value type
(Get-Process).GetType()

# Sorting the services based on status
Get-Service | Sort-Object status

Get-Service | Sort-Object status -Descending

# Get a service with the help of its name
Get-Service -Name "msi*"
Get-Service -Name "*app*" | Sort-Object name

# Get all the services based on their status
Get-Service | Where-Object {$_.Status -eq 'stopped'}
Get-Service | Where-Object {$_.Status -eq 'running'}

# Get a service with the name based on its status
Get-Service -Name "msi*" | Where-Object {$_.Status -eq 'stopped'}
```

> __Both applications and services have processes associated with them.__

[reference](https://superuser.com/a/209658)
