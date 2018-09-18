## Loops
* while loop
* do-while loop
* for loop
* foreach &rarr; to iterate over Array, ArrayList, HashTables

```powershell
# While loop
$i = 1
while($i -le 10) {
  Write-Output $i
  $i += 1
}

# Do-While loop
$i = 1
do {
    Write-Output $i
    $i++
}while($i -le 10)

# For loop
for($i=0; $i -le 10; $i++){
  Write-Output $i
}

# looping over an array
$names = @("Jon Snow", "Daenerys", "Cersei", "Baelish")
# Method 1
# Printing in the order
for($i=0; $i -le $names.Count; $i++){
  Write-Output $names[$i]
}
# Prinitng in reverse order
for($i=$names.Count; $i -ge 0  ; $i--){
  Write-Output $names[$i]
}

# Method 2
foreach($name in $names){
Write-Output $name
}

# looping over hash table
$my_bio = @{
    "name" = "Black Panther";
    "age" = 30;
    "country" = "Wakanda";
}

foreach($key in $my_bio.Keys){
  $val = "$key :  " + $my_bio[$key]
  Write-Output $val
}
```