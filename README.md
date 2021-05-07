# Rob's Gitting Started

This entire project is starting out as an opinionated, specific guide for "Future Rob". "Present Rob" has been using SVN and would like to change, so this is mostly a beginner's guide, but also it is a re-brainwashing document.

But who cares? Let's see the **topics/scenarios** that I want documented.

- Start a new project from scratch
- Make a change to an existing project
- TODO: what next?

---

## Start a new project from scratch

Start with a non-existent folder and end up with a repo on GitHub.

1. Create the folder while initializing a brand-new repo.
```
> git init git-docs
```

2. Navigate to the folder.
```
> cd git-docs
```

3. Open in VS Code.
```
> code .
```

4. Create the `README.md` file (however you want).

5. Stage the file.
```
> git add README.md
```
> This is the same as checking the box on the TortoiseSVN Commit window.

6. Commit the changes.
```
> git commit -m "Added the README.md file"
```
> This only commits the change that we staged LOCALLY. "It ain't on GitHub yet!"

7. Create a blank repo on GitHub (figure it out yourself) and then copy the new repo's URL.

8. Point our local repo to the remote repo that we created and verify it.
```
> git remote add origin https://github.com/eb35/git-docs.git
> git remote -v
```

9. Push our repo on up to GitHub.
```
> git push origin master
```

---

## Make a change to an existing project
