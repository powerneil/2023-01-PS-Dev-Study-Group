# Challenge 5 - PowerShell Input / Output
## Introduction
Reading and writing files is a fundamental part of working with any shell especially a CLI. PowerShell has built-in support for many common file types and associated cmdlets to work with them.  There are also modules that will extend PowerShell's capabilities to work with even more files - like for example Excel files. 

Combining PowerShell error handling and I/O is a worthwhile exercise.  

Let's learn about some of PowerShell's Input/Output capabilities by attempting the following challenges.  

## Challenge A - Reading JSON
- Demonstrate reading a JSON file from the web and converting it into a PowerShell object.\
_Hint: use the same example as in the TechThoughts video 7_
    - Why do you want to convert the JSON object to a PowerShell object and not simply use the JSON object as-is?
- Why is exporting data from PowerShell into JSON files better than using CSV files? (Or is it?)

## Challenge B - Read and interpret a log file
- Use a switch function nested in a for loop to create a sample log file that looks like this:
    ```log
    [INFO]Normal Operations
    [INFO]Normal Operations
    [INFO]Normal Operations
    [INFO]Normal Operations
    [ERROR]192.168.1.5 unable to access
    [INFO]Normal Operations
    [INFO]Normal Operations
    [INFO]Normal Operations
    [INFO]Normal Operations
    [INFO]Normal Operations
    [INFO]Normal Operations
    [ERROR]192.168.1.10 unable to access
    [INFO]Normal Operations
    [INFO]Normal Operations
    [INFO]Normal Operations
    ```
    _Hint: If you struggle with this, consider just manually creating the log file by copy/paste the above._
- Read the log file into a PS variable.
- Write only the errors to the terminal.
- Create a regex pattern that will show all the log file entries that contain an IP address.
- Use the `-like` comparison operator to show only log file entries that contain IP addresses.
- Add more content to the logfile by using `Add-Content`.
- What's the deal with the trailing newline when creating a file with `Out-File`?

## Challenge C - Relative Paths
- Use the `Resolve-Path` cmdlet to clarify the `$HOME` environment variable.
    - What does this actually mean?
- Where will the following code create a file? `New-Item -Path '~\test.txt'`
    - How can we test what will happen if we remove the file created in the previous step?
- How can you find out what the current directory is?
    - What is the command to display the current directory in CMD, and what is it in PowerShell?
    - Is there another PowerShell command that also displays the current directory?

## Challenge D - Error Handling
- Manually create a text file that contains several URLs.  Some of them should be fictitious, others should resolve properly.
- Create a PowerShell script that reads the text file and tests each URL for validity.  Use try/catch to accomplish the error handling.
- The script should create a new logfile that lists the URL and if was valid.
- Extra credit: 
    - First check if the log file exists, if not create one, if it does, just append to the log for each subsequent test you do.

Example log file:
```log
[WARNING] 2023/01/04 11:00 - Log file not found, creating new
[INFO] 2023/01/04 11:00 - Script started
[ERROR] 2023/01/04 11:00 - Could not read from input file, terminating.
[INFO] 2023/01/04 11:01 - Script started
[INFO] 2023/01/04 11:01 - Successfully read from input file urls.txt
[INFO] 2023/01/04 11:01 - google.com - Valid
[INFO] 2023/01/04 11:01 - microsoft.com - Valid
[WARNING] 2023/01/04 11:02 - nope.no - Invalid
[INFO] 2023/01/04 11:02 - Script ended
```

## Challenge E - Quick Directories
- In a temporary directory, create a subdirectory named for each of the modules of the course.
    - Extra credit: Do this with PowerShell instead of File Explorer
- Within each of the module directories, create a subdirectory named for each of the students in the class.
- Using a PowerShell flow control mechanism, replicate that structure in a second temporary folder, but don't include any files from the first temporary directory.\
_Hint: Don't use_ `Copy-Item`.
- Rename each of the directories you created in the previous step by prepending the letter 'M'.
- Rename each of the directories you created in the previous step by replacing the prepended letter 'M' with 'N'. 
- Clean-up the both temporary directories.
