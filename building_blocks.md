## Building Blocks of Programming
### Variables
* __Variable names begin with `$` symbol__

```powershell
# Declaring and initializing the variable
$my_name = "Rashik"
New-Variable -Name "my_name" -Value "Rashik"

# This modifies the existing variables value if it exists or else it will create the new variable
Set-Variable -Name "my_name" -Value "Rashik"


# Accessing a variable
$my_name

# To declare a global variable
$global:var_name = "This can be accessed throughout the current instance of shell"

# To get list of all the variables(user-defined and pre-definied) present in the current instance of shell
Get-Variable

# To delete the data stored in variable but not variable.
# Value of variable becomes Null
Clear-Variable

# To delete a variable and its value from its scope in which its defined(user-defined)
Remove-Variable -Name "my_name"

# Define the read-only or constant variables whose value cannot be modified once its defined
Set-Variable const_var -option Constant -value  100
Set-Variable readonly_var -option Readonly -value  100
```

### Data-Type &amp; TypeCasting
* Type of the data stored in the variable is known as Data-Type
* PowerShell automatically chooses the data-type when the variable was initialized.(similar to JavaScript, Python, Golang)
* Common Data-Types are __String, Integer, Boolean, Double etc__.
```powershell
# Check the type of data in the specific variable
$my_name = "Rashik"
$my_name.GetType() # Output: String
```
### Operators
#### Arithmetic Operators
```powershell
$marks1 = 85
$marks2 = 77

$marksTotal = $marks1 + $marks2 #Output: 162

$marksPercentage = ($marksTotal / 200) * 100 #Output: 81

$remainder = $marks1 % $marks2 #Output: 8
```

#### String Operators
> __*NOTE:*__ Try to use double quotes instead of single quotes both are not same.<br/>
> Double quotes __*resolve the variables to its value*__ where as single quotes do not resolve the variables to its value<br/>
> If you dont want to resolve the variable to its value and you're using double quotes then simply use the __`__ character which is known as escape character

```powershell
$var_string = "This is a random string."

#To check length of the string
$var_string.Length #Output: 24

# To check if it contains the specified word
$var_string.Contains("random") #Output: True
$var_string.Contains("Random") #Output: False

# To check the position of the given word in string
$var_string.IndexOf("random") #Output: 10
$var_string.IndexOf("Random") #Output: -1

# Conver the string to UpperCase
$var_string.ToUpper()

# Conver the string to LowerCase
$var_string.ToLower()

#Replace a word or letter in a string
$var_string.Replace("random", "simple")

# Write paragraphs which contain qutoes simply include in @""@
$new_string = @"
This paragraph contains "quotes inside quotes".
"@

# If dont want resolve variables present in the string then use single quotes
$new_string = '
This paragraph contains "quotes inside quotes".
'
``` 
> __Quick note:__ To get all the methods available on specific data type can be accessed easily by ``` $var_name | Get-Member ```

### TypeCasting

```powershell
# once the variable declared like below the data of the variable must be of type declared before the variable name
# This is most preferred and common way of type-casting
[int]$age = 20

# once the variable declared like below any kind of can be assigned to the variable
$age = [int]20

```
