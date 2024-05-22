# Git Collaborative Workflow Tutorial

## Forking a Repository

> 1.  Go to the Github page for the repository in question
>
> 2.  Click on "Fork" in the top right corner
>     <img src="./img/fork.png" alt="fork" width="75%" height="75%">
>
> 3.  Set the owner of the fork to yourself and click "Create fork"
>     <img src="./img/fork2.png" alt="fork" width="75%" height="75%">

---

## Clone the forked repository

> Clone the forked repository to your machine by running
>
> `git clone <repository_address>`
>
> Example:
>
> `git clone git@github.com:my_name/bluewave_collaborative_git.git`

---

## Set up the original repository as a remote

> You will want to be able to push and pull from the original repository. To do so, run:
>
> `git remote add <remote_name> <original_repository_address>`
>
> Example:
>
> ```
> git remote add upstream git@github.com:popnfresh234 bluewave_collaborative_git.git
> ```

---

## Fetching changes from upstream and merging

> You will often want to start from the latest code from the original project. To do so, run
>
> `git fetch <original_repository_remote>`
>
> Example:
>
> `git fetch upstream`
>
> Then, checkout the branch in **your forked repository** that you want to merge into, often master:
>
> `git checkout <branch_name>`
>
> Example:
>
> `git checkout master`
>
> Finally, merge the branch from the remote repository into your branch:
>
> `git merge <remote> <branch_name>`
>
> Example:
>
> `git merge upstream master`
>
> This will merge the remote master branch from the original repository into your forked repository's master branch
>
> Your code on your forked repository's master is now up to date with master of the original repository. This is a great place to create a new branch and start on a new feature.

---

## Creating and Checking out a Branch

It's a good idea to create a branch for features on your project.

### Creating a Branch

> Create a branch by running:
>
> `git branch <branch_name`
>
> Example:
>
> `git branch feat/my-feature`
>
> Your team will have their own naming conventions, but I like to use:
>
> Feature:
>
> `feat/<descriptive_feature_name`
>
> Fixes:
>
> `fix/<descriptive_fix_name`
>
> Whatever convention you choose, try to make the names descriptive

### Checking Out a Branch

> To switch to a branch and work on it, run
>
> `git checkout <branch_name>`
>
> Example:
>
> `git checkout feat/my-feature>`
>
> You are now ready to start working on your feature

_Hint_

> Creating and checking out a branch can be combined in one command:
>
> `git checkout -b <branch_name>`
>
> Example:
>
> `git checkout -b feat/my_feature`

---

## Adding and Committing Changes

### Adding to Git

> Now that you've made some changes, you will want to add them to git. To do so, you have some options.
>
> To add all of your changes in your project to git, run:
>
> `git add .`
>
> To add a specific file to git, run:
>
> `git add <filename>`
>
> ### Committing to Git
>
> Now that you've added your changes, it's time to commit:
>
> `git commit -m "<descriptive_change_message>"`
>
> If you are addressing an issue that has been opened on Github, you can add that to your commit message
>
> Example:
>
> `git commit -m "Added my name to Readme file, resolves #31"`

---

## Pushing Your Branch

> You've committed your code, now it's time to share it. To do so, we can push our branch to a repository. You will likely want to push your branch to the original repository so it can be merged in. You can do so by running:
>
> `git push <original_repository_remote> <branch_name>`
>
> Example:
>
> `git push upstream feat/my-feature`
>
> You can also push to your own repository:
>
> `git push feat/my-feature`
>
> This is useful if your branch isn't ready to merge into the original repository yet, or if you want to merge it into your own codebase.

---

## Making a Pull Request

> Finally, it's time to get our feature branch merged into the codebase.
>
> Head over to Github and go to the original repository. You should see that your branch has made it there!
>
> <img src="./img/pr.png" alt="pull request" width="75%" height="75%">
>
> Click on "Compare & pull request" button and follow the directions there.

---

## Cleanup

> Once your pull request has been approved and your code has been merged in, you can delete your branch from both Github and your local machine.
>
> Before you delete, you will want to update your repository:
>
> ```
> git fetch upstream
> git checkout master
> git merge upstream/master
> ```
>
> Now your master branch is up to date, including your new feature.
>
> You can safely delete your feature branch:
>
> `git branch -d <branch_name`
>
> Example:
>
> `git branch -d feat/my-feature`
>
> To delete your branch on Github go to the branches page and follow the directions there.

---

## Afterword

This is a general description of a collaborative workflow based around forks and branches.

Each team will have a slightly different workflow and conventions, so please adapt this guide as needed.

The main takeaway is that by working on a fork, using branches, and making pull requests we add a great deal of safety to our project and can work together with a minimum of code conflict.
