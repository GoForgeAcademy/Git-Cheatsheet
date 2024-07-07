### GoForge Academy Git Cheatsheet

Learning how to use git in the terminal can be a huge headache at first, but it'll make more sense and become easier with practice.

Let's go over a few git commands you will be using a lot throughout your coding career. Each command will be followed by a short description, and if there are arguments to enter they will be represented as `<argument>`.

---

```
git init
```

* Creates a new git repository in the folder where this command is run. It's best to set up different folders for each new project to avoid nesting git repositories.

---

```
git add .
```

* Finds all the modified files in the current directory and stages the changes.

---

```
git commit -m 'Commit message here'
```

* Commits all the changes tracked with `git add` to the repository. This is analogous to saving a file in a standard GUI program. Once you've committed a version of your code, you can always go back to that point (unless you manually delete the commit data).

---

```
git push
```

* This uploads your latest commit of the branch you are currently on to GitHub (or other online repository). Pushing means you believe to have the latest version of the code. If you don't have the latest version of the code, git will tell you to `git pull`. After pulling and resolving any issues, you should be able to push again.

* In the chance that your current branch doesn't already exist in the remote repository on GitHub, git will tell you that you should set an upstream origin. Use the command it provides to do so.

---

```
git pull
```

* Pulling means you are requesting to download the latest code from the remote repository on GitHub. If no one else has pushed since you last pulled, git will tell you that you are `Already up to date.`

* Pulling often results in merge conflicts. Make sure to carefully resolve the conflicts and consult with your team if necessary.

---

```
git merge <target branch>
```

* Working from the branch that you wish to merge another branch's changes to, run this command with the `target branch`'s name. For example, if you have a `development` branch that you wish to merge changes from `experimental` to, make sure you checkout to `development` and then run `git merge experimental`.

* `git merge` can result in merge conflicts just like pulling. Keep an eye out for conflict heads! `>>>>>>>>> HEAD`

---

```
git merge --abort
```

* Aborting a merge is possible and worth doing if you find out you've made some serious mistakes when attempting to resolve conflicts.

---

```
git checkout <target branch>
```

* This is how you switch to another branch. You can switch to any branch by using its name, or revert to previous changes by pasting the first bit of a commit code in.

---

```
git checkout -b <new branch name>
```

* This two-in-one command will create a new branch with the name you specify, and then switch to it.

---

```
git branch
```

* Will show all local branches, with your current working branch highlighted in some way.

---

```
git branch -a
```

* Lists all branches, including remote GitHub branches, which will be designated as 'remote'. This is useful for checking out to a team member's remote branch to see their changes before they push.

---

```
git switch <remote branch>
```

* If you see a remote branch that you want on your machine, this command will allow you to create a local version of that branch.

---

```
git log
```
* Will display a list of commits in the current branch. If you are using VS Code, click the ^ terminal button to make this easier to read! Make note of the commit codes - you can use these to checkout to previous changes that you've committed in case you broke your code or are just unhappy with the current state of things.

---

```
git status
```

* Shows the status of the changes you have made to the current branch. This is useful for figuring out what you need to add and commit.

---

```
git remote -v
```

* If you are ever confused about where the remote code for your project is located, use this command to list them out (it's possible to have more than one remote).

---

```
git remote update
```

* This command refreshes information (such as branches) from the remote repositories. Use it if you don't see a remote branch on your local machine.

---

```
git rm --cached <file name>
```

* If you've pushed sensitive files that need to be removed from the repository (for example, a .env or any files that contain passwords/keys), this command will do the trick

---

```
git filter-branch --index-filter "git rm -rf --cached --ignore-unmatch <file name>" HEAD
```

* Use this command to completely remove a file from git's history (most often combined with `git rm --cached <file name>`). You may get some warnings, it's okay as long as you know which file you are targeting.

---

```
git push --force
```

* Sometimes required for pushing more complex changes, such as those caused by the filter-branch command above.

---

```
git blame
```

* A tool for figuring out who made certain changes to the code. Please blame responsibly 😉

---

One more quick note - if you make some error (for example, trying to push when there is a more recent version already on GitHub), git does an amazing job of prompting you with what you need to do. In these cases, git will often give you a command to run. It's usually a good idea to try out the command. If you are super uncertain about it, look the command up and see what it does, then ask for help if you are still confused.
