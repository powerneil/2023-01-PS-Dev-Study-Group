# Challenge 4 - PowerShell Object Model
## Introduction
The following excerpt is from [PowerShell 101](https://learn.microsoft.com/en-us/powershell/scripting/learn/ps101/03-discovering-objects?view=powershell-7.3).

>My first introduction to computers was a Commodore 64, but my first modern computer was a 286 12-Mhz IBM clone with 1 megabyte of memory, a 40-megabyte hard drive, and one 5-1/4 inch floppy disk drive with a CGA monitor running Microsoft DOS 3.3.
>
>Many IT Pros, like myself, are no stranger to the command line, but when the subject of objects, properties, and methods comes up, they get the deer in the headlights look and say, "I'm not a developer." Guess what? You don't have to be a developer to be successful with PowerShell. Don't get bogged down in the terminology. Not everything may make sense initially, but after a little hands-on experience you'll start to have those "light bulb" moments. "Aha! So that's what the book was talking about."
>
>`Get-Member` helps you discover what objects, properties, and methods are available for commands. Any command that produces object-based output can be piped to `Get-Member`. A property is a characteristic about an item. Your drivers license has a property called eye colour and the most common values for that property are blue and brown. A method is an action that can be taken on an item. In staying with the drivers license example, one of the methods is "Revoke" because the department of motor vehicles can revoke your drivers license.


## Challenge A - Variables
- Demonstrate the use of PowerShell variables and why it is useful or sometimes unavoidable?
- What is the difference between a user-defined variable and a system variable?
- What is *typecasting* and how is handled in PowerShell, maybe as compared to other programming languages?
- What is the difference between the following commands?
    - `$myVar = 'Hello world'`
    - `$myVar = "Hello world"`
    - `[String]$myVar = 'Hello world'`

## Challenge B - Pipeline
- Demonstrate the use of the PowerShell pipeline including the following cmdlets:
    - `Sort-Object`
    - `ForEach-Object`
    - `Format-Table` and `Format-List`
    - `Select-Object`
- Use `Measure-Object` and `Select-Object` in a consecutive piping arrangement.  
- Demonstrate the difference between the normal and the error pipeline.

Variables are processed from right to left - whatever is to the right of the equal-sign (=) in assigned to the variable.  The pipeline is processed from left to right, the output of the cmdlet to the left of the pipe-symbol (|) is piped as the input-object of the cmdlet to the right. We can of course have several consecutive piped cmdlets.  
- Demonstrate the combined use of variable assignment and consecutive piping.  
    - Explain the order of operations in your example.

## Challenge C - Logic
- What does `Test-Path` do?
    - How can this be useful in a PowerShell script?
    - What logic operation would you typically use with `Test-Path`?
 - Before trying it for yourself, what do you think the following code would return and why is it producing these results?
    ```PowerShell
    $test1 = 'test'
    $test2 = $test2 -eq 'test'
    $test3 = $test1 = $test2 
    $test1
    $test2
    $test3
    ```

- Write a PowerShell script that counts the number of directories and calculates the total file-size of a given path.

- What is the difference between `$myObject = @()`, `$myObject = @{}`, and `$myObject = 'abc'`
    - Why does `$myObject = 'abc'; $myObject[2]` result in `c`?

## Challenge D - Sub-objects
Consider the following code and then answer the questions.
```PowerShell
$object = @()
$object += New-Object -TypeName psobject -Property @{
    Title = 'PowerShell Basics'
    URL   = @(
        'https://docs.microsoft.com/en-us/powershell/scripting/powershell-scripting', 
        'https://learn.microsoft.com/en-us/powershell/scripting/overview?view=powershell-7.3'
    ) 
    Score = 20
}
$object += New-Object -TypeName psobject -Property @{
    Title = 'PowerShell Tips and Tricks'
    URL   = @(
        'https://docs.microsoft.com/en-us/powershell/scripting/tips-and-tricks',
        'https://learn.microsoft.com/en-us/powershell/scripting/discover-powershell?view=powershell-7.3'
    )
    Score = 50
}
$object += New-Object -TypeName psobject -Property @{
    Title = 'PowerShell Advanced Techniques'
    URL   = @(
        'https://docs.microsoft.com/en-us/powershell/scripting/advanced-techniques',
        'https://learn.microsoft.com/en-us/powershell/scripting/learn/deep-dives/overview?view=powershell-7.3'
    )
    Score = 70
}

$object | Select-Object Title, URL | Sort-Object Score -Descending | Select-Object -First 2
$object | Export-Csv -Path 'obj.csv'
```
- Explain each line of the above code.
- The code above works, but there is a logic error (bug) in the code.  Can you figure out what's wrong and fix it?\
_Hint: Pipe order..._
- There is something wrong with the exported CSV file.  What's wrong with it and how would you go about fixing it?\
_Hint:_ `(Get-ChildItem -Path 'c:\' -Directory) -join '; '`
- Rather than using the trick in the previous point, can you export the file in a more modern format that doesn't have this issue?

## Challenge E - Spooky Calculator
Write a PowerShell script that watches the processes on the local machine for calculator being launched. If it's launched, close it and launch Excel instead. _Hint: Are infinite loops bad things?_