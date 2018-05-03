# Cleaning up history prior to creating a pull request
The idea of cleaning up your branch's history before creating a pull request can be a controversial topic.
Some project managers require some level of cleanup and some do not. Sometimes it is up to the developer to 
decide how much (if any) cleanup is done before creating a pull request.
[Here are some of the factors](cleanup_b4_pr_discussion.md) to consider when deciding how much (if any) clean
up you may want to do before creating a pull request.
We will also explain how to perform some of the cleanup options.
This discussion assumes we are using in a fork/clone development workflow.

In this example, we will be cleaning up a local branch named `wip_feature_abc` before creating a pull request to have 
the changes in the branch merged into the organization's master branch. We used the branch name prefix `wip_` to
indicate that this a `work in progress` branch.

The following steps may be more detailed 
than the steps you may use once you are familiar with this process. Hopefully, these detailed steps will help you
understand the process.

First we will run a couple of `git log` commands to review the commits in branch `wip_feature_abc`that will be
squashed into one commit.

```bash
git log master..wip_feature_abc --oneline
f5d8e32 (HEAD -> wip_feature_abc, origin/wip_feature_abc) Replacing uses of reference with remote
1b83923 Renamed reference to remote
73654be Wording change
f1cb0ca Creating place holder for cloning using ssh docs
c57514f Changed from SSH to HTTPS for cloning
```

The results show there are 5 commits in the branch `wip_feature_abc`. If we do a `git log -6 --oneline`, we
will see the commit from which the `wip_feature_abc` branch was created.

```bash
git log -6 --oneline
f5d8e32 (HEAD -> wip_feature_abc, origin/wip_feature_abc) Replacing uses of reference with remote
1b83923 Renamed reference to remote
73654be Wording change
f1cb0ca Creating place holder for cloning using ssh docs
c57514f Changed from SSH to HTTPS for cloning
2d742e4 Added setup step 2
```

In this case we can see the branch `wip_feature_abc` was started from commit 2d742e4 on the master branch
and consists of commits c57514f, f1cb0ca, 73654be, 1b83923, and f5d8e32. 

We want to squash those 5 commits into one commit that contains all of the changes from those 5 commits. 
First we create a new branch named `feature_abc`, removing the `wip_` prefix. This new branch will be
the branch that we use to create the pull request.

```bash
$ git checkout -b feature_abc master
Switched to a new branch 'feature_abc'
```

At this point branch `feature_abc` is exactly the same as branch `master`. Both branches point to the commit 2d742e4.
We will execute a `git merge --squash wip_feature_abc` to squash all 5 commits from the `wip_feature_abc` branch into
one set of changes in the working directory. 

```bash
git merge --squash wip_setup_step_1_and_2_b
Squash commit -- not updating HEAD
Automatic merge went well; stopped before committing as requested
```

We can issue a `git status` command to see which files have been changed by the 5 commits in the `wip_feature_abc` branch.

```bash
 git status
On branch feature_abc
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    new file:   cloning_using_ssh.md
    modified:   fork-clone-workflow.md
    modified:   git-glossary.md
 ```
 
 Next we issue a `git commit` command to create one new commit that contains all of the changes that were
 in the 5 commits from the `wip_feature_abc` branch.
 
 ```bash
  git commit -m "Changes based on feedback on last pull request"
[feature_abc 8bb0fa7] Changes based on feedback on last pull request
 3 files changed, 34 insertions(+), 25 deletions(-)
 create mode 100644 cloning_using_ssh.md
 ```
 
 We now have a new branch named `feature_abc` that contains one new commit and that new commit has all of the
 changes that were in the 5 commits in the `wip_feature_abc` branch.
 
 We can push the new branch to origin, go to github and create a clean pull request for the `feature_abc` branch.
 
 ```bash
 git push origin feature_abc
 ```
