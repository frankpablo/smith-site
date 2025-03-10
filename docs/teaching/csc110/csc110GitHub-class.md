---
layout: default
title: CSC110GithHub-class
parent: CSC110
grand_parent: Teaching
nav_order: 3
has_children: false
# permalink: /docs/teaching/csc110home/
---

<!-- # Instructions 

  1. Go to the [GitHub classroom for the course](https://classroom.github.com/classrooms/8136643-smithcollege-classroom-csc110-s25)
  1. Obtain the first assignment: [hello-world](https://classroom.github.com/a/bXQpxF7O)
 -->

# What is GitHub

GitHub allows you to save files and folders online and it lets you track changes made by one or many people editing that information. It uses **git**, which is a version control system that saves who changed what and when, and it let's you move "back" to previous versions and "roll back time" when needed.


## How does GitHub work

### Get a GitHub account

Every student in class needs to have their own GitHub account. It is free. 
When opening your account, do the best you can to use a name similar to your username at Smith.
For example, if my name is Pablo Frank Bolton, I would love to use "pfrank". If that is taken, I could use "pfrankbolton" or "pfrank80" or something lke that.

You don't strictly need an account to use git, but it makes things easier for novices.

### Repositories

Github saves projects in repositories. We call each a "repo". 

A repo saved online is called a "remote repo", and a copy of that remote on your local computer is simply called your "local repo". 

There are many ways to create a repo and use it, but in this class, this is what we'll do:

  1. Your instructor will distribute a link that let's you copy a template repo so you get your own. This is called "forking a repo".
  2. Once you fork a repo, two things will happen: 
      a. A repo under your account will be created with an exact copy of the template repo. We'll call this your "remote repo" since it is stored online. 
      b. If the instructor set up a "coding environment" for you, your remote repo will be opened in a "local" coding environment (more on this later). In this class, we'll use GitHub codespaces to edit your repos.
  3. You then work on your assignment by editing the desired python files, checking syntax, and testing, and when ready, you...
  4. Save "waypoints" of your progress. 
  5. When you submit the last "waypoint" you are done and your repo is already submitted. The instructor can see its last submission and grade it.

### How Do You save "Waypoints"?

When using git, every repo can have tracking of changes so that every little thing could be "undone" if necessary. The steps to save your work are:

  1. Pull: Before making ANY changes, always pull from the repo so you have the most updated version of the repo contents. 
  2. Edit: Make some edits and check your code runs (has correct syntax) even if it does not do everything you need it to do yet. 
  3. Stage: You must then **stage** the changes. This means that you have git add the current changes to the list of things you want to save on your waypoint.
  4. Repeat: You could then do more edits (go to 2) but then you'd have to stage those changes as well. Once you feel you've made and staged enough changes so that you want to save your current "waypoint", you are ready to commit.
  5. Prepare a commit message: Before fully committing, prepare a commit message. It is very important that you add a commit message before committing. Usually, these are short: "added the foo(num) function" or "fixed the bug in bar()"
  6. Commit: committing is saving a group of edits that constitute the changes you want recorded. The difference between the current state of the project and the previous commit will constitute the changes made if you perform an "undo", in case you need to roll back. Note that a commit is not an upload. A commit is still only saved on your local repo and the changes are not yet submitted "online".
  7. Repeat: You can do steps 2-6 until you are ready to upload or submit the accumulated changes stored in the sequence of commits.
  8. Push: pushing, in git, means uploading all your commits to the repo that is stored remotely. In Codespaces or VSCode, an option exists for performing a "Commit and Sync". This really only means that, before performing a Push, a Pull is done. However, if your changes conflict with changes made by someone else, then a conflict may arise that needs to be resolved (more on this later).


## Codespaces vs VSCode on your laptop

VSCode let's you edit files, run them, and explore and create directories on your computer. We call this an IDE or an integrated development environment.
The usual way people work with git is that they: 

  1. fork a repo
  2. pull any changes (not the first time if you just forked it)
  3. do edits, stage changes, commit them, and push

However, you can also use an in-browser IDE that GitHub provides. It is called a Codespace and it acts as-if it were on your local laptop. So even though you have not downloaded the remote repo to your laptop, the act of using a codespace to work on it makes a temporary local repo that you can edit and for which you can stage and commit changes, which you eventually push.


## Working in Codespaces or VSCode version control

While you can work only using the terminal on your laptop, most people prefer using an IDE. In both VSCode and Codespaces, the procedure looks like this:

### In Codespaces

A Codespace is opened in two ways: An instructor might have it open automatically when you accept (fork) an assignment repo, or you might have to open it from your remote repo. Here are all the steps:

  1. Open your remote on GitHub (example hw02): <br>
  ![OH location](../../../assets/images/csc110/codespace01_repo.png)
  2. Open a codespace from your remote: <br>
  ![OH location](../../../assets/images/csc110/codespace02_open.png)
  3. Before any edits, version control has no changes to stage. Go to the version control page (using the left side menu): <br>
  ![OH location](../../../assets/images/csc110/codespace03_version.png)
  4. Perform some edits: <br>
  ![OH location](../../../assets/images/csc110/codespace04_edits01.png)<br>
  and also:
  ![OH location](../../../assets/images/csc110/codespace05_edits02.png)<br>
  5. After running to check it compiles, go to the test area: <br>
  ![OH location](../../../assets/images/csc110/codespace06_test_area.png)
  6. Run the tests: <br>
  ![OH location](../../../assets/images/csc110/codespace07_test_results.png)
  7. After edits are made, go to the version control page (using the left side menu) and stage changes ( + symbol): <br>
  ![OH location](../../../assets/images/csc110/codespace08_version.png)
  8. After staging the changes, now there is something to commit (but dont commit yet): <br>
  ![OH location](../../../assets/images/csc110/codespace09_staged.png)
  9. Add a commit message before committing: <br>
  ![OH location](../../../assets/images/csc110/codespace10_message.png)
  10. Pressing commit adds one "local" waypoint to the list of commits: <br>
  ![OH location](../../../assets/images/csc110/codespace11_committed.png)
  11. You can perform some more edits (make sure it compiles even if does not pass more tests): <br>
  ![OH location](../../../assets/images/csc110/codespace12_edits03.png)<br>
  12. After edits are made, go to the version control page and stage changes ( + symbol): <br>
  ![OH location](../../../assets/images/csc110/codespace13_version02.png)
  13. Add a commit message before committing: <br>
  ![OH location](../../../assets/images/csc110/codespace14_message02.png)
  14. When ready, pull and push your commits by pressing commit and Sync: <br>
  ![OH location](../../../assets/images/csc110/codespace15_commit_and_sync.png)
  15. Once pushed, the changes can be seen in the remote repo: <br>
  ![OH location](../../../assets/images/csc110/codespace16_repo02.png)


### In VSCode

Go to the top-level directory of your local repo. If you don;t have a local repo yet, you will clone it by using the following command: `git clone <repo link>` (you can get the link from the GitHub repo info). Once you have a local repo, this is how one works with it in VSCode:

  1. Open your remote on GitHub (example hw02) and copy the clone link: <br>
  ![OH location](../../../assets/images/csc110/vscode01_clone_link.png)
  2. On VSCode, open the command pallete (Mac: Cmd+Shift+P  or Win: Ctrl+Shift+P), 
  search for "Clone" and press the option called **Git:Clone**, and then paste the clone link: <br>
  ![OH location](../../../assets/images/csc110/vscode02_paste_link.png)
  3. Select the directory where you want the local repo ( our Documents/csc110 is good choice): <br>
  ![OH location](../../../assets/images/csc110/vscode03_select_dir.png)
  4. Note that the version tree might already show previous commits from your instructor: <br>
  ![OH location](../../../assets/images/csc110/vscode04_version.png)
  5. Make some edits (make sure it compiles even if you don't pass tests): <br>
  ![OH location](../../../assets/images/csc110/vscode05_edits01.png)
  6. In version control, remember to stage your changes: <br>
  ![OH location](../../../assets/images/csc110/vscode06_stage.png)
  7. Add a commit message and commit: <br>
  ![OH location](../../../assets/images/csc110/vscode07_msg_commit.png)
  8. You can make more edits (again, make sure it compiles): <br>
  ![OH location](../../../assets/images/csc110/vscode08_edits02.png)
  9. Remember to stage any changes: <br>
  ![OH location](../../../assets/images/csc110/vscode09_stage02.png)
  10. When ready to sync, add a last commit message and commit and Sync: <br>
  ![OH location](../../../assets/images/csc110/vscode10_msg_commit_sync.png)
  11. Note your changes are visible in the remote: <br>
  ![OH location](../../../assets/images/csc110/vscode11_repo02.png)


## Troubleshooting

When you push, there are errors indicating there is a conflict: this usually happens if someone else made changes that you did not pull. It can also happen if you made changes through more than one codespace tab or if you disconnected between making a change and committing and pushing. 

The way to resolve this is to resolve the conflicts. Before resolving any conflicts, it is a good idea to save a copy of the edited file (in case something is lost) and then perform a merge. 

You would run the following instructions, in the terminal (inside the top directory of the repo), one by one **without the comments**:


Configure pull to merge as default strategy:

  ```
  git config pull.rebase false
  ```


After this, it is possible to pull and then push as normal. You can do this on the terminal:

Pull previous changes and merge with your own

```
git pull    
```

After this instruction, a window will ope in the editor with a bunch of comented out text. This is where you manually insert a commit message for your action tesolving the conflicts. 

You only need to add a line above the text indicating the commit message. For example: `Resolving commit conflicts`, and then click on the check mark that accepts the message (top right of the editor window).


Push your own commits to the remote  

```                   
git push                     
```



<!-- 
  1. click on the button "sign up and Try out" <br>
  ![sign up](../../../assets/images/csc110/lecture01/signUp.png){:width="250px"}<br>
  or [click here](https://www.pythonanywhere.com/pricing/)
  1. Click on "Create a Beginner account"<br>
  ![beginner](../../../assets/images/csc110/lecture01/beginnerAccount.png){:width="250px"}
  1. The fill out the form that appears with the following data:
      * **Your Smith username** (not some nickname); (if it is already in use, add a number to it: e.g. pfrank007)
      * use your Smith email
      * pick an easy-to-remember password and save it somewhere!!
      * Agree to the Terms and Conditions, the Privacy and Cookies Policy, and confirm that you are at least 13 years old.<br>
      ![beginner](../../../assets/images/csc110/lecture01/registerform.png){:width="500px"}
  1. You should verify your Smith email
  1. You should arrive at the Account for your account.
  1. If you do not see this page, look for the word "Account" on the top right (in the thin blue bar at the top of the page) and click it. The Account page looks like this:<br>
  ![account](../../../assets/images/csc110/lecture01/account.png){:width="900px"}<br><br>

  1. **IGNORE THIS TAB** and go to the **Education** tab<br>
  ![account](../../../assets/images/csc110/lecture01/educationTab.png){:width="900px"}
  1. In the text input line (in red) write the following username: **pfrank** and click the checkmark to accept<br>
  ![account](../../../assets/images/csc110/lecture01/add_pfrank.png){:width="900px"}<br><br>
  1. Once you have done this, look for the "Dashboard" link on the top (below the blue line) and click it:<br>
  ![account](../../../assets/images/csc110/lecture01/dashboard.png){:width="900px"}<br><br>
  1. We will go over this in class. For now, feel free to do the tutorial (green box that might appear in the top), but do not do the steps that say "Now it's time to check out some of the Education-specific features". At that point, press the button to "**Close this tutorial**"
-->