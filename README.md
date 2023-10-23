# PowerShell Development Study Group
Author: [Neil du Plessis](https://www.linkedin.com/in/neildup/)\
Last Edit: 2023/01/06

## Introduction
Welcome to the PowerShell Development Study Group. 

_You don't have to do anything (fork or clone, etc.) to this repo at this time - that will come later.  For now you can simply use it to access this overview and the challenges that will be listed below._

_**Study group**_ is not a course – we’re all going to be learning the topic together and take turns to prepare and present a module to the rest of the group in a session per module.  During each session we will listen to the participant who’s turn it is and have an open discussion on the topic of the day.  

Please refer to the [Welcome PowerPoint](</01 Welcome/PS Dev Study Group.pptx>) presentation for additional details. 

## Session Flow
You are required to prepare for each study group session and we will be using the following flow for the sessions:

### Before the session:
- Review the [course materials](#courseware) and do additional research as necessary.
- Complete the [challenge](#challenges) for the module.
- Create a [tutorial](#tutorials) if it's your turn to present at the upcoming session.\
(You may choose to do this anyway even if it isn't your turn - it's great practice!)

### During the session:
- Present your tutorial (if it's your turn).
- Q&A session where the group discusses the topic of the day.
- Confirm and schedule next session.

## Modules
Our study group will be covering the following modules:\
_Modules are allocated to individuals to present at a study group session._
|Module|Student|
|---|---|
|1. Introduction to PowerShell  | _Student 1_
|2. Development Environment | _Student 2_
|3. Source Control | _Student 3_
|4. PowerShell Object Model | _Student 4_
|5. Input/Output | _Student 5_
|6. Scripts and Functions | _Student 6_
|7. Cloud Management | _Student 7_
|8. Capstone Project | _Everyone_ 

## Courseware
Our primary courseware for group is the [TechThoughts Learn PowerShell](https://www.youtube.com/playlist?list=PL2j0_s2VJe2hzQuQyn6yfMS2olhhs4UnQ) playlist, but you are encouraged to find additional research materials. This study group's modules and related challenges do generally follow the structure of the above-linked videos, but there are some variation and overlap.  So, you may want to watch a few videos ahead to complete each of the modules in this study group.

## Workspace Structure
We will be using the following workspace (folder) structure.  This will become relevant after module 3, so don't worry about this too much at this time if you've never worked with code version control before.

_Warning: Deviating from this structure is likely to have your pull requests rejected._ 😝
- 01 Welcome (Contains the Welcome PowerPoint)
<details><summary>02 Tutorials (If it's your turn to present, you should create a folder with your name here to store your work)</summary>

- T01 - Intro to PS
    - your-name
    - other-student-name
    - ... 
- T02 - Development Env
    - your-name
    - other-student-name
    - ... 
- T03 - Source Control
    - your-name
    - other-student-name
    - ... 
- ...

</details>

<details><summary>03 Challenges (Each session has a challenge for you to complete.  Create a folder with your name here if you want to save files.)</summary>

- C01 - Intro to PS
    - your-name
    - other-student-name
    - ... 
- C02 - Development Env
    - your-name
    - other-student-name
    - ... 
- C03 - Source Control
    - your-name
    - other-student-name
    - ... 
- ...

</details>

## Tutorials
Everyone in the study group will have an opportunity to present one of the sessions.  You are not restricted as to how you want to approach this, but it is preferred that you create a tutorial using MarkDown.  An example is provided as part of the repo:\
[T03 - Source Control](</02 Tutorials/T03 - Source Control/Neil/T03 - Source Control.md>).

If you're unfamiliar with MarkDown, don't worry - you'll learn more about it as we make progress after Module-2.  For now you can simply create a text file (in notepad for example) with descriptions and step-by-step instructions for the student to follow. 

By means of demonstration of what should be in your tutorial, here's an example of a simple tutorial written in a text file:
```text
Tutorial - Showing the files in the current directory
=====================================================

Introduction
------------

Showing the files in the current directory is a basic command in any shell.
You might be familiar with `dir` in Windows command prompt shell or `ls` in Linux Bash shell.
Although those commands work and achieve the same results in PowerShell, they
are really just pre-programmed aliases for the PowerShell command `Get-ChildItem`. 


Practice
--------

- Open a PowerShell terminal
- Type `dir` and review the results
- Type `ls` and review the resiults (they're identical)
- Now type `Get-ChildItem` and review the results (identical again)
- Type `Get-Alias dir` to see how PowerShell translates the commands
```

Literally the very same text file rendered as a MarkDown file produces the following:

>Tutorial - Showing the files in the current directory
>=====================================================
>
>Introduction
>------------
>
>Showing the files in the current directory is a basic command in any shell.
>You might be familiar with `dir` in Windows command prompt shell or `ls` in Linux Bash shell.
>Although those commands work and achieve the same results in PowerShell, they
>are really just pre-programmed aliases for the PowerShell command `Get-ChildItem`. 
>
>
>Practice
>--------
>
>- Open a PowerShell terminal
>- Type `dir` and review the results
>- Type `ls` and review the results (they're identical)
>- Now type `Get-ChildItem` and review the results (identical again)
>- Type `Get-Alias dir` to see how PowerShell translates the commands

_**Isn't that super-cool!?**_ 😲

You can learn more about MarkDown and writing on GitHub here: [About writing and formatting on GitHub](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/about-writing-and-formatting-on-github).

## Challenges
A challenge is provided for each of the modules and is made up of one to five tasks.  They challenge your understanding of the module, and give you the opportunity to practice what you've learned.\
_Pro tip: If it's your turn to present a module in a session, you could use your solution to the challenge as the content for your tutorial._

Except if you're using the challenge as your tutorial, you don't have to present your challenge solutions, but we would still encourage you to use a lot of code comments in your challenge solutions for later reference. You're also welcome to ask questions about the challenges in the study group sessions for discussion.

As mentioned above, please add your challenge solutions to the appropriate place in the workspace structure.  (Don't worry if you don't quite know how to do this yet. You will learn about Git and GitHub in Module-3.)

- [C01 - Intro to PS](</03 Challenges/C01 - Intro to PS/C01 - Intro to PS.md>)
- [C02 - Development Environment](</03 Challenges/C02 - Development Env/C02 - Development Environment.md>)
- [C03 - Source Control](</03 Challenges/C03 - Source Control/C03 - Source Control.md>)
- [C04 - Object Model](</03 Challenges/C04 - Object Model/C04 - Object Model.md>)
- [C05 - PS IO](</03 Challenges/C05 - IO/C05 - PS IO.md>)
- [C06 - Scripts](</03 Challenges/C06 - Scripts/C06 - Scripts.md>)
- [C07 - Cloud](</03 Challenges/C07 - Cloud/C07 - Cloud.md>)
- [C08 - Capstone](</03 Challenges/C08 - Capstone/C08 - Capstone.md>)

## Next Steps
Let's get coding!
- Check out the first few videos of the [courseware](#courseware).
- Tackle the [challenge](#challenges) for the first module.
- If it's your turn to present at the next session, prepare a [tutorial](#tutorials)



### See you at the next session and good luck! 🚀