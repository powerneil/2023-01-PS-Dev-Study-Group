# Challenge 1 - Introduction to PowerShell
## Introduction
Before Windows, there was no Graphical User Interface (GUI) that we take for granted today.  Our only interface with computers were the command line interface (CLI). 

The word “shell”, is used to describe a program that allows the user to give commands to the computer.  So technically, a CLI and GUI are both shells.  

## Challenge A - Just Three Commands
Do the following all from PowerShell without the help of IntelliSense in the VSCode editor:
- Demonstrate how you can figure out how to use PowerShell with just these three cmdlets:
    - `Get-Command`
    - `Get-Help`
    - `Get-Member`
- What other basic PowerShell commands / cmdlets do you think are essential?

Consider the following code and sample response below. Answer the related questions:
```PowerShell
Get-Service -Name w32time | Get-Member
```
```Output
 TypeName: System.ServiceProcess.ServiceController

Name                      MemberType    Definition
----                      ----------    ----------
Name                      AliasProperty Name = ServiceName
RequiredServices          AliasProperty RequiredServices = ServicesDependedOn
Disposed                  Event         System.EventHandler Disposed(System.Object, Sy...
Close                     Method        void Close()
Continue                  Method        void Continue()
CreateObjRef              Method        System.Runtime.Remoting.ObjRef CreateObjRef(ty...
Dispose                   Method        void Dispose(), void IDisposable.Dispose()
Equals                    Method        bool Equals(System.Object obj)
...
Start                     Method        void Start(), void Start(string[] args)
Stop                      Method        void Stop()
WaitForStatus             Method        void WaitForStatus(System.ServiceProcess.Servi...
CanPauseAndContinue       Property      bool CanPauseAndContinue {get;}
CanShutdown               Property      bool CanShutdown {get;}
CanStop                   Property      bool CanStop {get;}
Container                 Property      System.ComponentModel.IContainer Container {get;}
DependentServices         Property      System.ServiceProcess.ServiceController[] Depe...
DisplayName               Property      string DisplayName {get;set;}
MachineName               Property      string MachineName {get;set;}
ServiceHandle             Property      System.Runtime.InteropServices.SafeHandle Serv...
ServiceName               Property      string ServiceName {get;set;}
...
```
- What is the difference between a property and a method?
- Try `Get-Date | Get-Member`, what kind of object is returned by `Get-Date`?
- How can we return the date in the _ShortDate_ format using a method of the object that is returned by `Get-Date`?
    - What's special about calling a method of an object, and why do you need to do it this way?
    - What type of object is returned by the method?
    - Why is this important?

Consider the following cmdlets.  Answer the related questions:
```PowerShell
Get-ChildItem -Path Cert:\LocalMachine\CA
$HOME
Get-ChildItem -Path $HOME
```
- What does the $HOME variable refer to?
- What does the _Cert:_ drive refer to?
- What other _drives_ are available?
- What cmdlet should you use to list all the items in the _Environment_ provider (_drive_)?
    - What exactly is the _Environment_ provider?



## Challenge B - Throwback to MS-DOS
MS-DOS was the Microsoft OS and its CLI was called the command interpreter (COMMAND.COM), that still survives today in modern Windows as the command prompt (CMD).  UNIX called their CLI Bash; still called the same today in Linux.

PowerShell is a more modern and powerful CLI shell but remains backwards-compatible with command prompt commands, mostly by aliasing the commands to their PowerShell equivalents. 

Do the following all from PowerShell: 
- Launch the command prompt (not PowerShell) and type `help`.  This will list the most common CMD commands and how to use them. 
- Change directory with `cd` and figure out why this command still works in PowerShell.\
*Hint: PowerShell has it's own command to change the current directory.*
- In a directory that contains files, use the `dir` command and explain its use in PowerShell.
- Create a directory using the CMD command, then using the PowerShell equivalent.
- Create a new file in the directory you created using a PowerShell cmdlet.  Is there another way to create a file?\
_(Hint: redirection operator.)_
- Add some text in your newly created file.  Also, display the content of your file.  How can you open the file for editing without using the GUI or notepad?\
_(Hint: you can launch applications from PowerShell.)_
- Create another directory and copy your file to it.
- Delete your file from the first directory.
- Move the file from the second directory to the first (where you just deleted the file).
- Demonstrate a few more DOS commands and their PowerShell equivalents.
- Explore a few alternatives for creating files.
    - Redirection operator
    - New-Item
    - Out-File


