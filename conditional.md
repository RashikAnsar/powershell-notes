## If-Else

```powershell
# Example 1
if (40 -eq (2*20)) {
    echo "true "
} else {
    echo "false"
}

# Example 2
[int]$num = Read-Host "Enter a number to check its odd or even"
if ($num % 2 -eq 0) {
    Write-Host "It's EVEN number" -ForegroundColor Cyan
} else {
    Write-Host "It's ODD number" -ForegroundColor Yellow
}

# Example 3
[int]$num2 = Read-Host "Enter a number"
if (-not ($num2 -le 100)) {
    Write-Output "Entered number $num2 is less than 100" 
}

# Example 4
[int]$num3 = Read-Host "Enter a number"
if (($num3 -gt 100) -and ($num3 -lt 1000)) {
    Write-Output "Entered number $num3 is somewhere between 100 and 1000"
} elseif($num3 -le 100) {
    Write-Output "Entered number $num3 is less-than or equal to 100"
} else {
    Write-Output "Entered number $num3 is more-than or equal to 1000"
}
```
## Switch statement
```powershell
[int]$num = Read-Host "Enter a number"
switch($num) {
    10 {"Entered number $num is equal to 10"}
    100 {"Entered number $num is equal to 100"}
    1000 {"Entered number $num is equal to 1000"}
    default {"Entered number $num is not equal to 10,100,1000"}
}
```