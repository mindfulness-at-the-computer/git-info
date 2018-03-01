# Git Glossary 

This git glossary contains definitions of terms used in this repository.

There is another dcoument that describes a mental model of git that
when understood can help one master git concepts at a deeper level. 

## commit
As a noun: A single point in history of a repository. The entire history of a project is represented as a set
of interrelated commits. Each commit is uniquely identified by a 40-character hexadecimal string which is created using
a hash function, also referred to has the SHA of the commit. Sometimes the SHA is abbreviated to the 
first 7 characters of the 40-character string.

As a verb: The action of storing a new snapshot of the project's state in the Git history, by creating a new commit. 

## fork
A fork is a copy of a repository. Forking a repository allows you to freely experiment with changes without
affecting the original project. Forks can be used to propose changes to someone else's project or as a starting
point for your own project.

Forking a repository is usually performed using the web interface for the remote hosting service (sush as [github](#github)).
The forked remote repository maintains a connection to the remote repository from which it was forked.

## commit object
An object which contains the information about a particular commit.

## git
`git` is a modern version control system used to maintain a history of changes to source code for a project. `git` has a 
distributed architecture and is an examnple of a DVCS (Distrubuted Version Control System). Rather than have only a single
place where the full version historyof the software is stored (like CVS or Subversion), in `git` every developer's working copy
of the code is also a repository that can contain the full history of all changes.

## github
`github` is a website and a service that maintains remote git repositories for project teams. Developers can interact with 
these remote repositories stored on gtihub using the web interface. If you clone a repository to your development
machine, you can interact with the remote repository using the `git` command line interface.

## github account
You must have an account to make changes to repositories stored on `github`. There are two types of github accounts, organization
and individual. The organization account is often where the main repository for large open source projects resides.
The person (or persons) with access to the organization account control who can make changes to the remote repositories owned by
the organization account.

Invidivual accounts are needed by developers who may want to make changes to repositories owned by organizational accounts when
the [fork/clone development workflow](fork-clone-workflow.md) is beihng used by the organization.
When individuals want to make changes to a organization repository they can create a pull request. The pull request is reviewed
and if approved will be merged into the organization repository.

## object database

## repository
A collection of [references](#references) to commit objects and an [object database](#object-database) of commit objects. 


## references
A string name that points to a commit. A reference also includes information about where the [commit](#commit) is located.
For the [fork/clone development workflow](fork-clone-workflow.md) the commit will be in one of three locations. 

1. A local clone on a developer's computer
1. The origin repository in [github](#github), which is your remote [fork](#fork)
1. The upstream repository in [github](#github), which is the organization's remote repository
