# Simple fork/clone development workflow

A typical fork/clone development workflow is described here. This information is intended 
for someone new to open source development and git source code control. The fork/clone
development workflow is not the only workflow possible. In some situations developers
do not fork the organizational repository but rather clone the organizational repository
directly. In this document we address only the fork/clone development workflow, not the
workflow in which forks are not used.

## Assumptions
1. [github](git-glosasry.md#github) is the source code control system used for the project.
1. You have aleady created a [github account](git-glossary.md#github-account). Examples here use username `joeuser`.
1. You know the github URL for the repository on which you will be working. Examples here use https://github.com/mindfulness-at-the-computer/git-info
1. You will at least start work on the project using the command level interface to [git](git-glossary.md#git].

## Step 1 - Create your own fork
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

You can try this our using the https://github.com/mindfulness-at-the-computer/git-info repository. 
Go to https://github.com/mindfulness-at-the-computer/git-info and you will see the main page for this repository.
Click the Fork button in the upper right hand corner of the page and you will end up with your
own version of the https://github.com/mindfulness-at-the-computer/git-info reository. If your github
username is `joeuser`, the URL for your version of the repository will be
https://github.com/joeuser/git-info.

## Step 2 - Make a local clone of your fork
This step is perfomed on the development system you will use to work on the source code 
for the project. 
### Work in progress (taking a snapshot of work on 2/27/18)


