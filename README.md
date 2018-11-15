# Learning Git workflows: Marvel Movies lesson
Demo for Juniata's IT-342 class

This lesson is to be done with at least one peer to demonstrate remote Git workflows.

## Lesson 1: preparation

On your system, please make sure you have Git installed on your system and a text editor of your choosing. Please configure 
your Github profile to use (SSH keys)[https://help.github.com/articles/connecting-to-github-with-ssh/].

Before starting the lessons, please load a terminal and Github. Email `nerdstein@gmail.com` with the Github usernames of 
those participating. I'll send an invite you will need to accept before assignment/merging is possible.

## Lesson 2: cloning repositories

Repositories are self-contained. You can have one on your local and one that would be considered a "remote". 

Github repositories are often remotes to local clones of the repository. By cloning, you automatically establish a connection 
to a remote repository.

On your system, run the following commands to clone to your local.

1. Go to your home directory: `cd ~` 
1. Clone with git: `git clone git@github.com:nerdstein/marvel-movies.git`

You should now have a `marvel-movies` directory.

## Lesson 2: issues

Making issues is a critical way to collaborate on improvements to projects. 

On github, perform the following steps.

1. Click on the (issues tab of the repository)[https://github.com/nerdstein/marvel-movies/issues]
1. Click on "New Issue" button
1. Describe your proposed change and save

## Lesson 3: working on an issue

1. assign yourself an issue and note the issue number, e.g. 4
1. on your local, make a new branch: `git checkout -b issue-4` where 4 is the issue number
1. perform the work described in the issue on your local
1. commit the work: `git commit -a -m "Issue 4: provide a description of your change`
1. verify the name of your remote repo: `git remote -v`, you should see `origin`
1. push your work to a remote branch on Github: `git push origin issue-4`
1. go to Github, you should see a "issue-4, compare and make pull request" message with a button
1. create a pull request and assign it to your peer
1. have your peer review your change through the "pull requests" tab on github
1. your peer should submit a review to accept or reject changes
1. once approved, your peer should merge the pull request

## Lesson 4: retrieving changes

Changes can be merged in at any time in the remote repository. It is best to frequently pull changes.

### New changes
When you start working on a new issue, it's best to load the most recent change to avoid any remote conflicts.

1. Load the default master branch on your local: `git checkout master`
1. Fetch all changes from remotes: `git fetch --all`
1. Synchronize your local master with the remote branch: `git reset --hard origin/master`

### Loading changes before merging
Changes to the upstream branch can happen while you are working on your changes. This often means changes cannot be merged 
when a pull request is made.

1. Have your peer merge a change while you are working on an issue on your local system
1. Commit your changes: `git commit -a -m "Issue 4: describe your work"`
1. Fetch all changes from remotes: `git fetch --all`
1. Rebase on the remote master branch: `git rebase origin/master`, note: this can be tricky if changes are made to the same files.
1. You may need to force push your rebase since the log of commits changed: `git push origin issue-4 --force`



