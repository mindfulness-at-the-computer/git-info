# Simple fork/clone development workflow

A typical fork/clone development workflow is described here. This information is intended 
for someone new to open source development and git source code control. The fork/clone
development workflow is not the only workflow possible. In some situations developers
do not fork the organizational repository but rather clone the organizational repository
directly. In this document we address only the fork/clone development workflow, not the
workflow in which forks are not used.

[Here is a diagram of the fork/clone development workflow](workflow.png)

## Assumptions
1. [github](git-glosasry.md#github) is the source code control system used for the project.
1. You have aleady created a personal [github account](git-glossary.md#github-account). Examples here use username `joeuser`.
1. You know the github URL for the repository on which you will be working. Examples here use https://github.com/mindfulness-at-the-computer/git-info
1. You will at least start work on the project using the command level interface to [git](git-glossary.md#git).

## Setup Step 1 - Create your own fork
This step is usually performed by logging into your personal [github account](git-glossary.md#github-account).
Locate the repository on which you will be working within the organization that owns the project. For exmaple,
this repository resides in the mindfulness-at-the-computer organization and the URL for this repository is
https://github.com/mindfulness-at-the-computer/git-info.

To create a [fork](git-glossary.md#fork) of the repository you want to use go to the main page of
the repository and click the `Fork` button in the upper right hand corner of the main page. Once
the [fork](git-glossary.md#fork) process is complete you will have your own version of the repository
in your [github account](git-glossary.md#github-account). The URL for your new repository will be the
same as the URL of the organization rerpository except that the organization name in the URL is 
replaced with your username.

You can try this using the https://github.com/mindfulness-at-the-computer/git-info repository. 
Go to https://github.com/mindfulness-at-the-computer/git-info and you will see the main page for this repository.
Click the Fork button in the upper right hand corner of the page and you will end up with your
own version of the https://github.com/mindfulness-at-the-computer/git-info reository. If your github
username is `joeuser`, the URL for your version of the repository will be
https://github.com/joeuser/git-info.

## Setup Step 2 - Make a local clone of your fork
This step is perfomed on the development system you will use to work on the source code 
for the project. You will [clone](git-glossary.md#clone) your fork on to your development machine. 
Then you will configure your clone so that it knows how to find the main (organizational) repository
from which the fork was created.

* Change directory to the location on your development machine where you want to store the clone. You can clone
to any location, but it is a good idea to keep your clones in a fixed location. In this example `joeuser` keeps
cloned repositories in the `/opt/repos` directory.
```bash
cd /opt/repos
```
* Clone your fork using the `git clone` command. You can find the URL of your fork on the main [gihub](git-glossary.md#github)
page of your fork. Click on the `Clone or download` button and a popup will show you the URL to use if you want to
`Clone with SSH`. The SSH option is the easiest option to use but requires that you have confiured configured your
[github](git-glossary.md#github) account with your public SSH key. As an alternative, you may select `Use HTTPS`. 
The HTTPS option uses a different URL and will require you to supply your [github](git-glossary.md#github)
account password each time you access your fork. The SSH option does not require you to supply your [gihub](git-glossary.md#github)
when accessing your fork.
```bash
git clone git@github.com:joeuser/git-info.git
```
* After executing the `git clone` command successfully, there will be a directory containing a clone of your fork.
```bash
$ ls -d git-info
git-info
```
* Change directory to the newly create reporitory directory (`git-info` in this example) to configure the local clone so that it
knows where to find the remote repository from which your fork was created. Your git clone maintains a set of
[references](git_glossary.md#references) to remote repositories. 
git automatically creates the `origin` reference when the clone is created. The `git remote -v` command lists the known
[references](git_glossary.md#references) and the values associated with each reference.
```bash
$ cd git-info
$ git remote -v
origin  git@github.com:joeuser/git-info.git (fetch)
origin  git@github.com:joeuser/git-info.git (push)
```
* By convention we use a reference named `upstream` to point to the remote repository from which your fork was 
created. We need to define the `upstream` remote reference by supplying the correct URL. You can find the 
URL of the repository from which you forked by clicking the link next to `forked from` label just below the name of your
fork on your fork's main [github](git-glossary.md#github) page. In this example, the fork was cloned from the 
`mindfulness-at-the-computer` main repository. Below is the git commnand used to define the `upstream` reference.
```bash
$ git remote add upstream git@github.com:mindfulness-at-the-computer/git-info.git
```
* After defining the `upstream` reference, you should see both `origin` and `upstream` remote [references](git_glossary.md#references).
```bash
$ git remote -v
origin  git@github.com:joeuser/git-info.git (fetch)
origin  git@github.com:joeuser/git-info.git (push)
upstream        git@github.com:mindfulness-at-the-computer/git-info.git (fetch)
upstream        git@github.com:mindfulness-at-the-computer/git-info.git (push)
```

## Setup Step 3 - Run unit tests on your fork
**TBD**

