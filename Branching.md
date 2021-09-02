# Branches

When you're working on a project, you're going to have a bunch of different features or ideas in progress at any given time – some of which are ready to go, and others which are not. Branching exists to help you manage this workflow.

When you create a branch in your project, you're creating an environment where you can try out new ideas. Changes you make on a branch _don't affect_ the main branch, so you're free to experiment and commit changes, safe in the knowledge that your branch won't be merged until it's ready to be reviewed by someone you're collaborating with.

One convention is such that the main branch should always be deployable. Because of this, all development occurs on separate branches which can then be _merged_ back into the main branch. Your branch name should be descriptive (e.g., `refactor-authentication`, `user-content-cache-key`, `make-retina-avatars`), so that others can see what is being worked on.

![Git Branch Example 1](https://s3.amazonaws.com/media-p.slid.es/uploads/huukhiemtong/images/24308/feature_branch_workflow.png)

In the above example, we see that all development of `features` take place on branches where as the main branch is left untouched.

![Git Branch Example 2](https://miro.medium.com/max/823/1*uUpzVOpdFw5V-tJ_YvgFmA.png)

In the second example, we can see a bit more complex branching, where there's a `develop` branch off of which all features are branched off. The idea is still the same, and at every release like v0.1, v0.2, v1.0, the code is merged back into `master`. This leaves other branches unaffected and is useful from making a mess.

A more complex branch workflow is shown below.

![](https://i.stack.imgur.com/jHzp4.png)

With that knowledge of branches and workflows that can be customised to any level, let's dive into how to use them.

## Branching Off!

You can do one of the two things, create a branch on Github and pull it down locally, or do the opposite and create a branch locally and push that up to Github.

### Creating Branch On Github And Then Pulling It Down

![](https://i.imgur.com/zmkjVwa.png)

After creating a branch, a complete copy of the branch you are branching off of, (maybe mostly the main branch) will be there on the newly created branch. From there you can pull the changes down to your local machine.

```sh
> git fetch <remote> # fetch all info about the remote and newly created branches etc. will default to the default remote if no remote is specified.
> git checkout <branch> # Switch to the new branch to start working.
```

### Creating A Branch Locally and then Pushing it up to Github.

In this case, we do the branching locally and push the branch up to Github to let it know about it.

- To create a new branch -

```sh
> git branch add <your_new_branch>
```

- Switch to that branch -

```sh
> git checkout <your_new_branch>
```

- Alternatively, you can do all in one go with the `-b` flag to `checkout`

```sh
> git checkout -b <your_new_branch>
```

- You can start working and when you are about to push it to Github, we push to a new branch

```sh
> git push <remote> <your_new_branch>
```

## We branched Off!

You can switch between branches using `checkout` command as earlier. Changes made in branches are completely seperate nad will not affect any other branches. This means any new files, modifications etc done on one branch, will not affect the other branches and will not be reflected in other branches.

## Bringing Changes Back To The Main Branch

Typically, there are **Pull Requests** on Github for this, but you can also merge locally.

```sh
# Switch to the branch where you want to merge the other branch
> git checkout main
```

```sh
# Merge the branch in
> git merge <your_branch_name>
```

Also, as the changes have been merged, you may want to delete the branch.

```sh
# Delete the stale branch
> git branch -D <your_branch_name>
```

For merging across branches usually its nice to make a Pull Request. Will be covered next.
