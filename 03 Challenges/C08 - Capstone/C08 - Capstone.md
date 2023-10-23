# Challenge 8 - Capstone Project
## Introduction
If you've made it this far, congratulations! We've come to the last challenge of the course.  I sincerely hope that you've learned a lot about PowerShell development and can find opportunities to use it to your advantage in your every-day professional life.  Maybe even in your personal life!?  

## Challenge - That one thing you've always wanted to do with PowerShell
Yes, that's right - the capstone project is completely open-ended.  You are now equipped with intermediate to advanced PowerShell skills, not to mention development skills.  The sky is the limit.  

Your challenge is to create a PowerShell script that accomplishes something you've always wanted to do or automate.  Maybe something you have to do in your current position or job.  Give it some thought and maybe experiment with a few ideas before tacking your idea head-on!

## Capstone Project Ideas
If you really can't think of something, here are a few examples of projects you could try:

### Bulk Rename 
Create a utility that will bulk rename files in a folder. If this sounds familiar, you've already started this project in one of the challenge exercises of Module-5. 

The idea is that if you have a folder full of files (photos perhaps) that have a non-descriptive name, you could use this function to give them all a more descriptive name.  

Here's an example:
```Text
img-333444.jpg
img-333445.jpg
img-333446.jpg
img-333447.jpg
othertestfile.txt
```

To be converted to:
```Text
2023-01-08 - Camping Trip - 33444 - SLR.jpg
2023-01-08 - Camping Trip - 33445 - SLR.jpg
2023-01-08 - Camping Trip - 33446 - SLR.jpg
2023-01-08 - Camping Trip - 33447 - SLR.jpg
2023-01-08 - Camping Trip - othertestfile - SLR.txt
```

- Create a script that loads a function into the current session, possibly called `Rename-Bulk`.
    - A function instead of a script to prevent the script file from being renamed as part of the process. E.g., run the script to load the function into the current session, you can call the function from the command line.
- Function help to be provided so that `Get-Help Rename-Bulk` provides properly structured help.
- Maybe add `[CmdletBinding]` to the function to let it impersonate a real cmdlet. You'll need to add what additional functionality is provided by this measure in the help, and probably add some code to make the function provide those capabilities. 
    - E.g., `-Verbose` to make the function write what it's doing to the terminal.
    - Could you make `-WhatIf` work here?
- The function should accept parameters like:
    - `-Path` location of the target folder where rename should take place.
    - `-RemoveLeft` removes the given number of characters from the left of the filename. (Obviously, keep the file type extension, just rename the file.)
    - `-RemoveRight` removes the given number of characters from the right of the filename.
    - `-KeepLeft`
    - `-KeepRight`
    - `-Append` Append the given string to the end of the filename. 
    - `-Prepend` Add the given string to the beginning of the filename.
    - `-Directory` Switch that tells the function to only rename sub-directories in the current directory and ignore files.
    - `-KeepUptoDelimiter` Keep everything before a specified delimiter.
    - `-KeepAfterDelimiter` Keep everything after a specified delimiter.
    - `-RemoveUptoDelimiter`
    - `-KeepUpToDelimiter`
    - Add more options you think might be useful.
- How can one deal with files that don't match the general pattern of other files in the folder? E.g., `othertestfile.txt`.
- Include error handling. For example, how will the script act if you specify `-RemoveLeft 20` but the filenames have only 10 characters filename. 
- Include input filtering. For example, will you allow negative numbers to be provided for the parameters, and how will this work?

### Copy named locations between Entra ID tenants
Create a script that will copy a defined named location from one tenant to another. 
- Use the Microsoft.Graph module.
- Parameterise the source and destination tenant IDs, and the named location name.
- Hint: \
 `Connect-MgGraph -TenantId $DestinationTenantId -Scopes @('Policy.Read.All', 'Policy.ReadWrite.ConditionalAccess')`
- Add error handling. (Don't overwrite existing locations with the same name.)
- What about copying conditional access policies too?

### Good luck!  And see you in the session. 👀