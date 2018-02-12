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

## commit object
An object which contains the information about a particular commit. 

## object database

## repository
A collection of [references](#references) to commit objects and an [object database](#object-database) of commit objects. 


## references
A string name that points to a commit. A reference also includes information about where the [commit](#commit) is located.
For fork-clone style development the commit will be in one of three locations. 

1. A local clone on a developer's computer
1. The origin repository in the cloud
1. The upstream repository in the cloud
