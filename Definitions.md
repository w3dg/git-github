# Git commands, Some terminology, Some examples

You can use [Github Desktop](https://desktop.github.com/) or [Git Kraken](https://www.gitkraken.com/) for the below commands instead, as a GUI option.

## `Git Commands`

- `git init` _initializes_ a brand new Git repository and begins tracking an existing directory/folder. It adds a _hidden subfolder_ `.git/` within the existing directory that houses the internal data structure required for version control and can be deleted (`rm -rf .git/`) if you want to stop git from tracking that directory.

- `git add` _stages_ a change. Git tracks changes to a developer's codebase, but it's necessary to stage and take a snapshot of the changes to include them in the project's history. This command performs staging, the first part of that two-step process. Any changes that are staged will become a part of the next snapshot and a part of the project's history. Staging and committing separately gives developers complete control over the history of their project without changing how they code and work.

- `git commit` _saves the snapshot_ to the project history and completes the change-tracking process. In short, a commit functions like taking a photo. Anything that's been staged with git add will become a part of the snapshot with `git commit`.

- `git status` _shows the status_ of changes as **untracked**, **modified**, or **staged**.

- `git push` _pushes_ your local commits up to a `remote`.

## Let's look at a detailed step by step explanation.

### Clone an existing repository

```
# download a repository on GitHub.com to our machine
git clone https://github.com/me/repo.git

# change into the `repo` directory
cd repo

# make changes, for example, edit `file1.md` and `file2.md` using the text editor

# stage the changed files
git add file1.md file2.md

# take a snapshot of the staging area (anything that's been added)
git commit -m "my snapshot"

# push changes to github
git push --set-upstream origin my-branch
```

We did not cover `branches` yet, that's coming up.

### Push an existing repository to Github

```
# create a new directory, and initialize it with git-specific functions
git init my-repo

# change into the `my-repo` directory
cd my-repo

# create the first file in the project
touch README.md

# git isn't aware of the file, stage it
git add README.md

# take a snapshot of the staging area
git commit -m "add README to initial commit"

# provide the path for the repository you created on github
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git

# push changes to github
git push --set-upstream origin main
```
