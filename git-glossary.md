# Git Glossary 

This git glossary contains definitions of terms used in this repository.

There is another dcoument that describes a mental model of git that
when understood can help one master git concepts at a deeper level. 

## clean commit history
A clean commit history is one where each commit is easy to understand and tells a story about how the project
evolved. It is clear when features were added and who added them. Each commit is a solid piece of work and
represents a milestone in the implementation of a feature or fix. 
This clean commit history is not something that you need to think about while implementing a feature or fix.
Rather make commits as often as makes sense to you and your work environment.
Once the change is complete, think about what would be most useful for others to know about the change,
compress the commits into the fewest commits needed (usually just one) and provide a good commit comment.
There are a variety of tools one can use to clean
up the commit history of local changes before creating a pull request to share those changes with the rest
of the project team. The `git merge --squash` command is one the options available for cleaning up local 
commit hsitory. The important concept is that the detailed steps (commits) that
were made while developing a feature or fix do not have to be the same detailed steps (commits)
shared with others.

Another aspect of a clean history is a linear history free of unnecessary merge commits. It is possible
to maintain a linear commit history by using the `git rebase` command on local changes before 
creating a pull request to share your changes with the rest of the project. See
[Merging vs. Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing) for more information.

## clone
A clone of a [github](#github) repository is a local copy of a repository residing on [github](#github). git maintains
a set of symbolc refernces to URL's for remote repositories. After the clone operation is complete, git sutomatically
creates a symbolic reference called `origin` to the remote URL from which the repository was cloned. The git 
command `git remote -v` lists the remote symbolic referneces that git know about along with the URL associated with
each remote symbol.

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


## remote
A string name that points to a repository. The value associated with a remote is the URL used to access the remote repository.
A remote serves as a short alias for a longer URL. 
For the [fork/clone development workflow](fork-clone-workflow.md) a repository will be in one of three locations. 

1. On your local machine. A local clone on a developer's computer
1. In your remote fork on github. The `origin` remote points to your [fork](#fork) in [github](#github), created automatically by the 'git clone` command.
1. In the remote organization on github.The `upstream` remote points to the main remote repository in [github](#github), manually created to point to the repository
from which your [fork](#fork) was created.
