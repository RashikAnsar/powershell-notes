## Comparison Operators
```powershell
# Equality Operator
1652 -eq (413 * 4) # True
"ABC" -eq "ABC" # True

"ABC" -ceq "ABC" # True (case sensitive equality operator)
"ABC" -ceq "abc" # False (case sensitive equality operator)

"ABC" -cne "XYZ" # True (case sensitive not equal operator)
200 -ne 500 # True

# Less-Than operator
21 -lt 22 # True 
22 -lt 21 # False 

# Less-Than Or Equal to operator
21 -le 22 # True 
21 -le 21 # True 
21 -le 20 # False 
# Similarly -gt, -ge operators for Greater-Than and Greater-Than Equal to

# like Operator
"PowerShell" -like "*shell" # True
"PowerShell" -clike "*shell" # False (case sensitive)

"PowerShell" -like "power*" # True
"PowerShell" -clike "power*" # False (case sensitive)

# Contains, not contains operators
"Bash", "PowerShell" -contains "PowerShell" # True
"Bash", "PowerShell" -contains "Shell" # False 
"Bash", "PowerShell" -notcontains "Shell" # True

# Match operator automatically generate a $matches variable
"Sunday" -match "sun" #True
$matches # Sun
```
[Comparison Operators reference](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_comparison_operators?view=powershell-6)