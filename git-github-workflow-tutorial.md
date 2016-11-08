

# Git, Github, & Workflow Tutorial

Now that you've been trained on our git and github workflow, it's time to put what you've learned into practice by completing this simple tutorial. In this example, we will be contributing to the https://github.com/Microsoft/Docs repository.

**NOTE:** This tutorial presupposes that you have already completed the steps described in [Initial Setup](readme.md#initial-setup).

## Fork the repo

Go to https://github.com/Microsoft/Docs and click the "Fork" button in the upper right-hand corner of the UI.
  
![Fork button](./media/tutorial/training-tutorial-fork.png)

If asked "Where should we fork this repository?", select your github username.

When the fork is complete, you will automatically be taken to "https://github.com/YOUR-GITHUB-USERNAME/Docs".

## Clone your fork locally

From your fork of the main repo (i.e. https://github.com/YOUR-GITHUB-USERNAME/Docs), click the green "Clone or download" button (again in the upper-right), and either manually copy the URL to your clipboard, or click the clipboard icon.
  
![Clone button](./media/tutorial/training-tutorial-clone.png)

Then, in Git Bash, change to the directory in which you wish to store your Git repos. Many contributors create a "docs" folder under `C:\Users\YOUR-WINDOWS-USERNAME` and store their repos there.
    
**TIP:**: In Git Bash, the tilde (~) corresponds to your "home directory"; i.e., in a Windows system, "C:\Users\YOUR-WINDOWS-USERNAME". So, after creating the "docs" subdirectory, you can move into it using `cd ~/docs`.
    
Enter `git clone COPIED-URL`. Once the clone is complete, change into the newly cloned directory. You'll know you are in a git repo because the branch name "master" will appear in parentheses.

![Git bash](./media/tutorial/training-tutorial-gitbash-clone.png)

## Create aliases to upstream and origin 

If you enter `git remote -v` at this point ("-v" for "view") you will see an alias already set:  "origin" = to your fork of https://github.com/Microsoft/Docs.  Origin always refers to the head of your clone.

You will want to create a second alias called "upstream", which is set to the main repo (i.e., https://github.com/Microsoft/Docs).  To do so, enter 'git remote add upstream http://github.com/Microsoft/Docs.git`.

## Embed your credentials into your aliases (optional) 

You don't have to perform this step but, if you don't, you will have to supply your github username and access token via a dialogue box when performing some operations.  Embedding your credentials into your aliases obviates this need.

First, go to https://github.com/settings/tokens and click "Generate a new Token". On the next screen, put "Git Bash" as a description, and click the green "Generate Token" button at the bottom (there's no need to check any of the boxes).  Lastly, copy the generated token (a 40-character alphanumeric string) to your clipboard (or click the clipboard icon) on the final screen.

Now return to Git Bash.  Delete the existing "origin" alias with `git remote remove origin`, and then recreate it in this format:  `git remote add origin http://GITHUB-USERNAME:NEWLY-CREATED-ACCESS-TOKEN@github.com/GITHUB-USERNAME/Docs.git`.  As before the "origin" alias points to your fork, but it now has your credentials embedded.

Now do likewise with "upstream": `git remote remove upstream` followed by `git remote add upstream http://GITHUB-USERNAME:NEWLY-CREATED-ACCESS-TOKEN@github.com/Microsoft/Docs.git`.
  
**IMPORTANT:**: When giving you a personal access token, Github warns that you will never again see it on their website. Fortunately, if you embed it into your aliases, you can later view it (and, more importanly, copy it for use in other repos) using the aforementioned `git remote -v` command.

## Sync the repo and create a working branch

Enter `git pull upstream master:BRANCH-NAME`. "BRANCH-NAME" can be anything you choose, but it's best to make it relevent to the changes you are making (in this instance, something like "training" or "tutorial"). 

**NOTE:**: Even though you are working in a clone of your fork ("origin"), you generally sync with the main repo ("upstream"). When other contributors make changes they will merge them into the main repo, so syncing with "upstream" ensures you have the most up-to-date files.

If you receive an error when attempting a sync, you have likely set up your "upstream" alias incorrectly. Review and repeat the steps above, if necessary.  

## Switch to your branch

Switch to your newly created branch using `git checkout BRANCH-NAME`. If successful, your comandline will now has BRANCH-NAME in the parentheses.

![Git bash](./media/tutorial/training-tutorial-gitbash-branch.png)

## Edit one or more files

Now you are ready to actually modify files.  The https://github.com/Microsoft/Docs repo has a number of dummy markdown files that you can experiment on, which you can find in Docs/samplefiles.  Using your chosen text editor, make and save changes to one or more of these files.

To view what files you've altered, you can enter `git status` in Git Bash.

![Git status](./media/tutorial/training-tutorial-gitbash-status.png)

To see the specific changes you've made to files, you can use `git diff`.

## Stage the files

Before you commit your changes to the local repo, you must first stage them using `git add`. You can either stage files individually by specifying their paths, or stage all files in your current directory and below with `git add .`.  

If you run `git status` afterward, you'll see that staged files appear in green, while unstaged files appear in red.

![Git add](./media/tutorial/training-tutorial-gitbash-add.png)

You can continue to make changes to staged and unstaged files alike, although you will need to re-add a file each time you change it further.

## Commit the files

When you are comfortable with all of your changes, you can commit them to the local repository using `git commit -m "YOUR COMMIT MESSAGE"`.  -m stands for "message", and allows you to annotate your changes.

If you run `git status` after a commit, you will see nothing. That's because, so far as Git is concerned, you are completely finished with your changes and ready to on a new set fresh.

## Push the changes to Github

You've now commited the changes to your local clone of the forked repository, but you still need to get them out to Github.  The command for this is `git push origin BRANCH-NAME`. 

**NOTE:**: When pushing you use "origin" (even though you pulled from "upstream"), because your goal is to get your changes into your fork. 

![Git commit and push](./media/tutorial/training-tutorial-gitbash-commit-push.png)

## Create a pull request

Lastly, you must "request" that the main repo "pull" your changes into its master branch, through a mechanism called a "pull request".  To do so, go to either your fork of the repo or the main repo on github, and click the "Create a Pull Request Button".

![Git commit and push](./media/tutorial/training-tutorial-pr.png)

On the next page, you want to set the base (the left-hand side) to the master branch of the main repo, and the head (the right-hand side) to the BRANCH-NAME branch of your fork.

![Git commit and push](./media/tutorial/training-tutorial-pr-compare.png)

When you are sure the base and head are correct, click "Create Pull Request"

**TIP:**: If you are lucky, Github will give you a yellow banner with a Compare & Pull Request button already configured for the changes you wish to merge. 
>
> ![Git auto PR](./media/tutorial/training-tutorial-pr-auto.png)
>
> You must still verify that the base and head are correct, though.

## What's Next

Now that you've cloned the Docs repo, you have the External Contributor's Guide on your local machine. Or you can continue to read it online at https://github.com/Microsoft/Docs/.
