
#### Apply commits from one branch to another branch with cherry-pick

Say you have created a commit in the wrong branch and you would like to reproduce that commit in the right branch,
then you can cherry-pick that commit and apply it to your current branch.

If you want to apply the last commit of branch `experiment` to the current branch:

    git cherry-pick experiment

If you want to apply commit `78c5f6` to the current branch:

    git cherry-pick 78c5f6
    

In both cases you will have a new commit in your current branch with the changes from the commit you cherry picked.

If the commit cannot be applied cleanly, you will have to resolve a merge conflict.
[This article](https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/) explains how to do that.

If you are using PyCharm then you can easily resolve merge conflicts using the **VCS - Git - Resolve conflicts** feature.