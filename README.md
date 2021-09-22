# Rob's Gitting Started

This entire project is starting out as an opinionated, specific guide for "Future Rob". "Present Rob" has been using SVN and would like to change, so this is mostly a beginner's guide, but also it is a re-brainwashing document.

But who cares? Let's see the **topics/scenarios** that I want documented.

- `IMPORTANT!` Set user name and email
- Start a new project from scratch
- Make a change to an existing project
- Complete a feature branch
- Checkout an existing remote branch
- Merge that branch

---

## Set user name and email

I didn't do this and it used out-dated info, but it still worked.

1. Set the global values.
```
🔰 git config --global user.name "Rob Henry"
🔰 git config --global user.email "roberthenry@email.com"
```

2. Verify the values.
```
🔰 git config --list
```

---

## Start a new project from scratch

Start with a non-existent folder and end up with a repo on GitHub.

1. Create the folder while initializing a brand-new repo.
```
🔰 git init git-docs
```

2. Navigate to the folder.
```
🔰 cd git-docs
```

3. Open in VS Code.
```
🔰 code .
```

4. Create the `README.md` file (however you want).

5. Stage the file.
```
🔰 git add README.md
```
> This is the same as checking the box on the TortoiseSVN Commit window.

6. Commit the changes.
```
🔰 git commit -m "Added the README.md file"
```
> This only commits the change that we staged LOCALLY. "It ain't on GitHub yet!"

7. Create a blank repo on GitHub (figure it out yourself) and then copy the new repo's URL.

8. Point our local repo to the remote repo that we created and verify it.
```
🔰 git remote add origin https://github.com/eb35/git-docs.git
🔰 git remote -v
```

9. Push our repo on up to GitHub.
```
🔰 git push origin master
```

---

## Make a change to an existing project

1. Start by getting the remote repo's URL.

2. Then clone the remote repo to your local machine
```
🔰 git clone https://github.com/eb35/git-docs.git
```

NOTE: You can specify the folder name or clone the repo into the current folder as well.
```
🔰 git clone https://github.com/eb35/git-docs.git folder-name
🔰 git clone https://github.com/eb35/git-docs.git .
```


3. Navigate to the folder.
```
🔰 cd git-docs
```

4. Open in VS Code and make changes to the file.
```
🔰 code .
```

5. Stage the changes. This time I'm using the period (.) to stage all the changes, instead of listing the files explicitly.
```
🔰 git add .
```

6. Commit the changes to the local repo. This time I'm making a multi-line comment.
```
🔰 git commit -m "
🔰 Adding an additional scenario
🔰 Only updating the readme
🔰 "
```

7. Push the changes to the remote repo.
```
🔰 git push
```

---

## Complete a feature branch

1. Clone the remote repo to your local machine and navigate to the folder
```
🔰 git clone https://github.com/eb35/git-docs.git
🔰 cd git-docs
```

2. Create a new branch and switch to it.
```
🔰 git branch chevron-icon
🔰 git checkout chevron-icon
```

3. Make your changes, stage them, and commit them.
```
🔰 git add .
🔰 git commit -m "trying out chevrons"
```

4. Push the brand-new branch AND the changes we made up to the remote repo.
```
🔰 git push --set-upstream origin chevron-icon
```

---

## Checkout an existing remote branch

So I might be missing a step because I had problems getting the remote branch changes after cloning the repo and then moving into the remote branch, but now this seems to work... A possible `fetch` command might fix your issue though 🙄.

1. Clone the remote repo to your local machine and navigate to the folder
```
🔰 git clone https://github.com/eb35/git-docs.git
🔰 cd git-docs
```

2. List all the branches (remote and local).
```
🔰 git branch -a
```

3. Do the normal checkout command to switch to the branch.
```
🔰 git checkout chevron-icon
```

> OR replace Steps #1-3 with the following command:
```
🔰 git clone https://github.com/eb35/git-docs.git -b chevron-icon
```


4. Make changes (like normal), stage them, commit them, and push them.
```
🔰 git add .
🔰 git commit -m "Hoping this works..."
🔰 git push
```

> This may only affect 🦊GitLab, but I had to run the following to checkout a remote branch. `git checkout -b branch-name origin/remote-branch-name`
```
🔰 git checkout -b chevron-icon origin/chevron-icon
```

## Merge that branch

You made a new branch (see above) or you contributed to a remote branch (see above), but now you're done and the branch has served its purpose and it's all been committed. Now merge that branch!

1. Make sure that your up-to-date on your branch.
```
🔰 git pull
```

2. Switch to the main branch (a.k.a. the Trunk) and make sure it is up-to-date.
```
🔰 git checkout master
🔰 git pull
```

3. Now merge it.
```
🔰 git merge chevron-icon
```

4. I guess you don't need to stage and commit the changes. You just need to push.
```
🔰 git push
```

> Again, this may only affect 🦊GitLab, but I had to run the following to push my local branch to the a remote branch. `git push -u origin branch-name` After the first time, you can just run `git push`.
```
🔰 git push -u origin chevron-icon
```