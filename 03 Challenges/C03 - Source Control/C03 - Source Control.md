# Challenge 3 - Source Control
## Introduction
Git and GitHub are the de-facto version control and code sharing platform (respectively) used by almost all developers.  PowerShell developers are no exception. In the challenges that follow, we are going to implement Git and publish our content to GitHub.

## Challenge A - Git CLI
Do all of the following from the terminal:
- Install Git on your Windows computer from the PowerShell integrated terminal in VSCode, then restart VSCode.  
    (If you're working on Mac or Linux you can skip this step.  However, this tutorial assumes that you're using Windows.)
- Configure your username and email address in the Git global settings.
- Create a new Git project and commit your first change.
- Create a new branch, make a change, and finally merge the branch into the master branch.

## Challenge B - Git in VSCode
Do all of the following in VSCode:
- Create a new workspace.
- Initialise a Git repository.
- Demonstrate the following:
    - Commit a change.
    - Create a branch.
    - Merge a branch.

## Challenge C - GitHub
- Log in or create an account on GitHub.
- GitHub flow: Complete the [Introduction to GitHub](https://github.com/skills/introduction-to-github) exercise in GitHub.\
_Don't skip the videos, they're delightful!_ 😊
- GitHub Forking: Complete the [First Contributions](https://github.com/firstcontributions/first-contributions) exercise on GitHub, but instead of using the CLI, use VSCode's built-in Git and GitHub integrated features.
    - Navigate to the page on GitHub where your pull request is pending.
    - Now that you've completed the First Contributions skill tutorial, review one of the other languages provided with the tutorial that you are familiar with.  Do you think the translation could be improved?  If so, describe step-by-step what you can do to update the translation and ask the owner of the repository to consider using your updated translation instead.
- Explain the difference between Git and GitHub by means of a demonstration.
- Publish a Git version-controlled project to GitHub from VSCode using its integrated features.
- Perform Challenge B again, this time syncing changes to GitHub.
    - Should one sync changes to GitHub for every single thing - how often is best practice?

## Challenge D - Course files
The course files have been published to GitHub in a public repo.  
You can access it here: [PS Dev Study Group](https://github.com/powerneil/2023-01-ps-dev-study-group)

You are going to fork the repo (create a copy of my repo on your own GitHub account) and work on your own copy of it.  The idea is that you will create a branch on your own fork of the repo for every study session. You can create tutorials (MarkDown), scripts, and whatever else relevant to the branch, committing and pushing changes to your own fork as you go along.  

Once we're finished with the session and you are satisfied with your work, you can ask for your branch to be merged back to my master branch of my repo via pull request.  Once all the pull requests from students are merged, you can sync your fork and continue with the next session. 

Of course, nothing prevents you from working on whatever session (branch) you want - the beauty of Git/GitHub is that you can work on whatever you want and sync when you're ready regardless of what any of the other team members are doing.  

Below is a diagram of how this is supposed to work.

```mermaid
    gitGraph
        commit id:"final"
        branch fork/main
        checkout fork/main
        branch session1
        checkout session1
        commit
        commit
        checkout main
        merge session1 tag: "Pull Request" type: HIGHLIGHT
        commit
        checkout fork/main
        merge main tag: "Sync fork" type: HIGHLIGHT
        branch session2
        checkout session2
        commit
        commit
        checkout main
        merge session2 tag: "Pull Request" type: HIGHLIGHT
        commit
        checkout fork/main
        merge main tag: "Sync fork" type: HIGHLIGHT
        branch session3
        checkout session3
        commit
        commit
        checkout main
        merge session3 tag: "Pull Request" type: HIGHLIGHT
        checkout main
        commit
        checkout fork/main
        merge main tag: "Sync fork" type: HIGHLIGHT

```

Use what you've learned in the _First Contributions_ tutorial to fork, clone, and branch the repo.  After our study session, you can submit a pull request which I'll review and merge into the main branch for the class.
