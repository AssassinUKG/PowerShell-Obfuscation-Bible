# PowahShell

## Obfuscating Boolean Values
It's super fun and easy to replace `$True` and `$False` values with other boolean equivalents, which are literaly unlimited.  
A boolean value in PowerShell can be replaced with at least the following. All of the examples below evaluate to `True`. You can reverse them to `False` simply by adding an exclamation mark before the expression (e.g., `![bool]1`):
 - Simple and complex logical substitutes (obviously):
 ```
 [bool]1254
 [bool]0x12AE
 [bool][convert]::ToInt32("111011", 2) # Converts a string to int from base 2 (binary)
 ![bool]$null
 ![bool]$False
 [bool]"Any non empty string"
 [bool](-12354893)   # Boolean typecast of a negative number returns True
 [bool](12 + (3 * 6))
 ```
 - Boolean type casting any class will return `True`:
 ```
 [bool][bool]
 [bool][char]
 [bool][int] 
 [bool][string]
 [bool][double]
 [bool][short]
 [bool][decimal]
 [bool][byte]
 [bool][timespan]
 [bool][datetime]
 
 [bool][System.Collections.ArrayList]
 [bool][System.Collections.CaseInsensitiveComparer]
 [bool][System.Collections.Hashtable]
 # Well, you get the point.
 ```
 - The result of a comparison:
 ```
 $x = (9999 -eq 9999) # Simple
 $x = ([math]::Round([math]::PI) -eq (4583 - 4580)) # Complex
 ```

 - Boolean type casting something you know will return a value Not equal to 0 (can also be a string, array, etc)
 ```
 [bool](Get-ChildItem -Path Env: | Where-Object {$_.Name -eq "username"})
 [bool]@(0x01BE)
 ```
[System.Data.AcceptRejectRule].Assembly.GlobalAssemblyCache
![System.Data.AcceptRejectRule].Assembly.GlobalAssemblyCache
i''e''x''
```

In loops and comparisons....