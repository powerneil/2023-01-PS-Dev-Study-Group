# Challenge 6 - PowerShell Scripts and Functions
## Introduction
So far in the course, we've been creating PowerShell files (.ps1) that contain code meant to be executed piecemeal - one line at a time, or maybe a few lines at a time by selecting it and running the selected code (F8). 

However, a PowerShell script is intended to be executed as a single complete file - this is what PowerShell scripting is all about.  

As part of a script you would sometimes want the script to complete the same subroutine repeatedly. We could use a function to accomplish this.  Your script could create a function that is only intended to be used inside your script, or alternatively, your script could create a function that is available in the shell after the script finished executing.  

We learned about scripts and functions in this module.  We can look at this module as the putting together all the building blocks we've learned about so far.  

## Challenge A - Folding a script file
By this time you will have noticed that VSCode allows you to collapse sections of your code to make it more readable - or maybe to temporarily hide the detail of a certain section of code.  You'll see collapse/expand handles in the gutter of your code.  (The gutter is the space between the code number and the start of the code.)  VSCode automatically allows you to collapse/expand code blocks (anything inside indented curly brackets).

In addition to the automatic collapse/expand, there is a way to tell VSCode to allow you to collapse larger sections of your code.  This is particularly helpful when you are creating code in a PowerShell file that is intended to be run separately from other sections of code.  

Your challenge is to demonstrate script folding in VSCode.

_Hint:_ `#region foo`

## Challenge B - Get-PublicIp
Create a PowerShell script that in turn creates a function in the current shell that will return the user's current public IP address.  The function should be called `Get-PublicIp` and should provide help when issuing `Get-Help Get-PublicIp`.

_Hint: Use the https://api.ipify.org API as demonstrated in the video._

## Challenge C - URL Tester Script, now featuring Functions
- Enhance the script you created in the previous challenge _(Challenge D - Error Handling)_ with the following:
    - Create a small function in your script called _Log-Message_ that adds content to your log fie.  Call the function every time your script wants to write to the log.
    - Create a function in the current shell called `Add-UrlTestFile` that will add additional URLs to the test URLs file.
        - The function should have a switchable parameter to alter the function to show the list of URLs from the file instead of adding one.
            - Is this the right thing to do or is there a more standard approach?
        - The function should have help so that `Get-Help Add-UrlTest` provides help including examples.
    - Convert the code that tests if the URL is valid to an internal function.
    - Made additional enhancements along the lines of scripts and functions as covered in this module.

