## Array
```powershell
# array declaration 1
$a = 10, 20, "my array", "Sample", 30, 40
# array declaration 2
$b = @(10,20, "my-array")

# Accessing value from array using index
$a[0] # [OUTPUT] 10
$a[1] # [OUTPUT] 20
$a[2] # [OUTPUT] my array

#Methods available on array using Get-Member
$a | Get-Member

# To access a range of elements from an array
Write-Output "The length of array a is " $a[1..3] #[OUTPUT] 20, my array, Sample

# To get the size of an array
Write-Output "The length of array a is " $a.Length #[OUTPUT] 6

# To join/combine/add two arrays
$c = $a + $b 
$c.Length # [OUTPUT] 9

# To know the index of the given value in an array
$a.IndexOf("Sample") # [OUTPUT] 3

# Array is a fixed size so we cannot add elements into it 
# so to overcome this there is an ArrayList Collection
$a.Add("Numeric") # [OUTPUT] ERROR: COLLECTION WAS A FIXED SIZE

# Checking whether the collection is fiexd size or not 
$a.IsFixedSize #[OUTPUT] True
```

## ArrayList
```powershell
# To create an ArrayList
$names = New-Object System.Collections.ArrayList

# Adding a single element into an ArrayList
$names.Add("Stark")

# Adding a range of elements into an ArrayList
$names.AddRange(("Jon Snow", "Daenerys", "Cersei", "Baelish")) 

# To Know the length of ArrayList
$names.Capacity # [OUTPUT] 5
$names.Count # [OUTPUT] 5

# Checking whether the collection is fiexd size or not 
$names.IsFixedSize #[OUTPUT] False
```
> Array's and ArrayList's are good for storing data but they are slow for searching data and they allows duplication of data as well. To overcome these problem there is another type of collection known as HashTable.

## Hash Table
* Hash Table also known as associative array (or) dictionary.
* It stores data in the form of key-value pairs
* Hash Table does not allow the duplication.
```powershell
# Hash Table
$my_bio = @{
    "name" = "Black Panther";
    "age" = 30;
    "country" = "Wakanda";
}

# To Know the number of items in hash table
$my_bio.Count #[OUTPUT] 3

# To get all the keys
$my_bio.Keys # [OUTPUT] name age country

# To get all the values 
$my_bio.Values 

# Access value of a specific key 
$my_bio.name

# Adding a key-value pair to hash table
$my_bio.Add("Original Name", "T'Challa")

# To Remove a key-value pair from hash table
$my_bio.Remove("Original Name")
```