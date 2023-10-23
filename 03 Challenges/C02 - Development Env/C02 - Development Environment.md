# Challenge 2 - Development Environment
## Introduction
When you launch the command prompt (CMD), Windows PowerShell, or PowerShell (Core) from Windows, you are presented with a single window with the CLI.  [Windows Terminal](https://learn.microsoft.com/en-us/windows/terminal/) is a modern host application for the command-line shells you already love, like Command Prompt, PowerShell, and bash (via Windows Subsystem for Linux (WSL)). Its main features include multiple tabs, panes, Unicode and UTF-8 character support, a GPU accelerated text rendering engine, and the ability to create your own themes and customize text, colours, backgrounds, and shortcuts. 

Going beyond the shell and terminal, you can combine several commands in the form of a script.  Scripts can execute a list of commands in sequence to accomplish a certain goal, instead of you having to type them one at a time.  Each shell has different kinds of scripts: for example, the command prompt has batch files (.BAT), bash has bash scripts, and the same with PowerShell in the form of PowerShell scripts (.PS1).  In fact, scripts have evolved to resemble fully fledged programming languages. This is why this course is is called **_PowerShell Developer_** - once you start writing PowerShell scrips you will quickly start learning software development techniques.

Historically, one would use a simple text editor to create scripts - in fact, some people still do today.  However, modern code editors have evolved to provide very powerful code authoring capabilities.  Windows PowerShell Integrated Scripting Environment (ISE) is a specialised code editor that was developed specifically for Windows PowerShell.  However, it only supports up to PowerShell 5 and is no longer being developed.  Most PowerShell developers have moved over to **Visual Studio Code** as the preferred IDE[^1] for writing PowerShell code. Although there are others, this course is going to assume VSCode as the code editor in use. 
[^1]: Integrated Development Environment

Let's start using Windows Terminal as our primary shell application and VSCode as our primary development environment for writing PowerShell scripts.  In the challenges that follow, we are going to learn about Windows Terminal and VSCode by installing and customising them.  In addition to the customisations requested by the challenge, add your own customisations to make the environment suite your needs and preferences.  As you learn more, you are likely to make more and more customisations - this is normal and a great way to get to know these tools.  

## Challenge A - Windows Terminal FTW
- Install PowerShell 7, VSCode, and Windows Terminal if you don't already have them installed.
    - How would you install them from PS if you didn't?
- Configure Windows Terminal as the default CLI for your OS and PowerShell (not Windows PowerShell) as the default terminal profile.
- Configure Windows Terminal drop-down menu to show terminal profiles in this order:
    - PowerShell
    - Windows PowerShell
    - Azure Cloud Shell
    - Command Prompt
- Customise the prompt of your PowerShell terminal profile.\
_(Hint: see the variable `$PROFILE` by typing it into Windows Terminal and pressing enter.)_
    - Nerd Fonts
    - Oh-my-posh
    - Terminal-Icons
- Why are customisations you make to terminal not also applied to VSCode's integrated terminal?
- What causes IntelliSense to do auto completions when using terminal or VSCode's integrated terminal?  (Not the VSCode editor, the terminal specifically.)
    - Instead of inline completion, can you configure the terminal to show a list of possible completions?
- Demonstrate a few of your own customisations (e.g., transparency...?)

## Challenge B - VSCode - PowerShell
- Install the PowerShell extension in VSCode.
    - What specific functionality enabled by this extension do you most appreciate?
- What other extensions have you installed and what do they do for you?
- What preferences have you configured in VSCode?  _(Hint: Watch related videos by TechThoughts and Justin Grote)_
- Customise VSCode's integrated terminal.\
_(Hint: see the variable `$PROFILE` by typing it into VSCode's integrated terminal and pressing enter.)_
    - Nerd Fonts
    - Oh-my-posh
    - Terminal-Icons
- Are you using different profile customisations for Terminal and VSCode?

## Challenge C - VSCode Customisation
- How can you install an extension in VSCode from PowerShell?
    - Write a PowerShell script that will install your favourite VSCode extensions.
- How do you open a file for editing in VSCode from the PS terminal?
- How do you navigate the File explorer in Windows from PowerShell?
- How can you create a portable VSCode installation?
- What is the Command palette in VSCode?
- What is your favourite VSCode keyboard shortcuts?

## Challenge D - VSCode Workspaces
- Explain and demonstrate the concept of a *Workspace* in VSCode. 
- Why is it critical to work on one Workspace at a time; one project at a time, instead of on several separate projects in the same workspace?
- Explain your strategy for saving projects locally (on your machine)?