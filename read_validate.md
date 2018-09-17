## Read, Validate and Write

```powershell
# Reading and validating the userdata
# [Validation][DataType]$Varname = Read-Host "Content"
# [Validation]$Varname = [DataType](Read-Host "Content")
[ValidateLength(3, 25)][string]$name = Read-Host "What is your name"
[ValidateRange(5,100)][int]$age = Read-Host "How old are you"
[DateTime]$date = Read-Host "What is the date on which you started learning PowerShell (mm/dd/yyyy)"
[ValidateSet("y", "Y","n","N")][char]$response = Read-Host "Are you a student (Y/N)"
$password = Read-Host "Enter password" -AsSecureString

Echo "========================================"
echo "Your name is : $name"
echo "Your age is: $age"
echo "date: $date"
echo "$response"
echo "passwotrd is: $password"
```
> If you're generally prinitng the data to console and you've no intention to use advanced features of powershell like pipeline then go with `Write-Host` or else go with `Write-Output`

> `Write-Host` Value cannot be stored in a PowerShell variable<br>
> `Write-Output` Value can be stored in a PowerShell variable

```powershell
Write-Host "Welcome to PowerShell" -ForegroundColor Cyan

Write-Host "How far you're to consider yourself a pro in PowerShell" -ForegroundColor Yellow -BackgroundColor Red

Write-Output "Hey, Its Write-Output"
Write-Error "Hey, Its Write-Error"
Write-Warning "Hey, Its Write-Warning"

Write-Verbose "Hey its Write-Verbose" -Verbose
Write-Debug "Hey its Write-Debug" -Debug

# The above statement of using Write-Host or Write-Output
# Checking Get-Member on both
Write-Output "WRITE-OUTPUT" | Get-Member
Write-Host "WRITE-HOST" | Get-Member # Error is output

$var_host = Write-Host "WRITE-HOST in variable"
$var_output = Write-Output "WRITE-OUTPUT in variable"

$var_host # no output
$var_output #[output] WRITE-OUTPUT in variable
```