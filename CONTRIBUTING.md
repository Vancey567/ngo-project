# How can I contribute?

- You can fix the typos (if any) in any documentation of this repo.
- You can check for any **unassigned** [issues](https://github.com/DevMatrix1/ngo-project/issues) and **comment** on that issue that you'd like to get that issue assigned to you. (Remember: Do not work on issues assigned to someone else and do not work on any issue without having it assigned to you.)
- Create issue if you see any bug and then once you get approved from the admins, you can assign yourself and start working on it.

# How can you make a **Pull Request** (PR)

**Note**: Steps 1, 2 and 3 are **one-time** steps required for setup. If you have already cloned the repo and added upstream, consider following this documentation from step 4.

1. **Forking repository**

Fork this repository using the **Fork** option at the top-right corner of this page. This will create your own copy of this repository. You'll be redirected to your forked repository. Copy the link of this repository (which will look like `https://github.com/<your-username>/ngo-project.git`) as you'll need it in the step 2.

2. **Cloning repository and Installing packages**

Clone your forked repository, this will download your copy of repository in your computer. To do this, open your terminal (command prompt/bash/git bash) and enter the following command, paste your link after the word **clone** without the **<>**.

```
git clone <link which you copied in the step 1>
```

Once you have cloned the repository, now you should go into the folder containing the repository. You can do that with:
```
cd ngo-project
```

Now you should install the required packages to run this project by doing:
```
npm install
```

3. **Adding remote repository**

Add the Dev_Matrix repository as a remote repository, so that you can anytime pull the latest changes from the Dev_matrix repository which is being deployed. This needs to be done only for the first time.

```
git remote add upstream https://github.com/DevMatrix1/ngo-project.git
```

4. **Getting the latest code from the main branch** (Can be skipped if you've cloned the repo just now)

If it's been quite a while after you have cloned the repo/made the last pull request, it's recommended to take a pull from the main branch. Reason being, there may be some changes which could have merged after you had cloned the repo/made the last pull request.

To do so, make sure you're in the main branch by checking out to the **main** branch:

```
git checkout main
```

Once you're in the **main** branch, it's time to take a pull:

```
git pull upstream main
```

Now that you've made sure that you've got latest changes, we can proceed to creating our branch

5. **Creating a new branch**

Let's create a new branch to work on. We require a different branch so that we always have a stable, working version in the default (develop) branch. We're not supposed to touch the **main** branch as it is the one getting deployed on production.

```
git checkout -b <branch-name>
```

We will try to name the branch according to the task we are going to perform in it. If it is going to be a `feature`, the branch name should begin with `feat` or `feature`. If it is going to be a `fix`, the branch name should begin with `fix` or `bugfix`. The branch name should be self-explanatory.
For example, if I want to work on a `feature` called `login-form`, the branch name will be **feature/login-form**. If it is going to be a `fix` in `navbar`, the branch name will be `fix/navbar`.
Command example:

```
git checkout -b feature/login-form
```

6. **Just do it!**

Perform the tasks you wanted to, can be anything, ranging from fixing simple typo to re-designing the whole page!

7. **Committing your changes**

Now you have made the changes, though they are saved in your system, Git doesn't know what changes you've done. So you have to **commit** your changes. First step is to add the files which you want to add to the staging area, the dot after **add** in the first command tells Git to check for changes in all the files. The second step is about committing your changes. The message part is short description of your commit, like "adds a login form on homepage". Please make sure NOT to have commit messages like "fix issue#34". When we look at the commit history, we should understand what a particular commit is supposed to do based on the commit message.

```
git add .
git commit -m "Write message about your commit"
```

8. **Making sure you have the latest changes from the main branch**

It may so happen that since the last time you cloned the repo/took a pull from main, some changes may be merged in the main branch. So to be on the safer side, we should have those changes as well.

In order to do that, we first checkout to **main** branch by:

```
git checkout main
```

Once we're in main, it's time to take a pull:

```
git pull upstream main
```

Now that our **local** main branch is in sync with **remote** main branch (of the Dev_Matrix Repository), we should let our branch know about the changes from the main branch (if any). To do so we first checkout to our branch:

```
git checkout <branch-name>
```

Once we're in our branch, we **rebase** our branch on top of the current main branch (we change the base of our branch, so that it appears as if we have worked from the time the latest changes were merged in the main branch). To do so:

```
git rebase main
```

9. **Pushing the code**

Now that we have made our changes plus we have the latest changes made by other contributors, we should push our code from **local** branch to the same branch on our **GitHub fork**. We do so by:

```
git push origin <branch-name>
```

For example, if the branch name is `feat/login-form`, we enter `git push origin feat/login-form`

The **origin** refers to your GitHub fork. You can check it by entering `git remote -v`, you should the link to your fork against **origin**.

10. **Making a pull request**

11. **Review stage**

Now the maintainers/admins will review your pull request. They might suggest some changes if required. You should then make the required changes in the **same branch**, commit them and push your changes to the **same branch** (follow the steps 7, 8 and 9 for the same).

12. **Congratulations on your first Pull Request in Dev_Matrix! 🎉**
