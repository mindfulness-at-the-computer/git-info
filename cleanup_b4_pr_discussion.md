# Cleaning up commit history before creating a pull request

It is important to realize that the frequency of and reasons for creating a commit vary from developer to
developer. On the high commit frequency end of that spectrum we find developers using
TDD (Test Driven Development). It is often the practice with TDD to create commits frequently,
as tests are developed and new tests pass. This is 
sometimes referred to as a `green light`. With TDD, you may want to create a commit to preserve the state
of the code for each `green light`. Even developers who are not using TDD may choose to create commits often 
in order to preserve the current state of the code. A developer may also want the added protection of committing 
often and pushing to origin so that they have an off-site copy of their latest changes. In this case a new
feature consists of a potentially long list of commits where each commit makes relaltively few changes. 
Let's call this the `many small commits` style of development.

On the other end of the spectrum, a developer my make all of the changes needed for a new feature before
making a commit. In this case a new feature consists of one or a small number of commts where each
commit makes many changes. Let's call this the `few large commits` style of development.

In some cases, it is a project requirement that there be only one commit for each new feature. In other
cases it is up to the developer to decide between `many small commits`, `few large commits`, or some 
combination of the two. Either by project requirement or personal choice a developer may need to 
create a pull request that contains one commit for the feature they are implementing. A developer
can work in the `many small commits` mode to satisfy their needs and then convert the many
commits into one commit before creating a pull request. The git term `squash` is used to describe 
the process of converting many commits into one commit. We will call this `squashing commits` and it
is one form of cleanup that a developer may want to perform before creating a pull request. The
process of `squashing commits` is described [here](cleanup_b4_pull_request.md).

Another form of cleanup that may be required or a developer may choose to perform is called `rebasing`.
The `rebasing` operation can be performed whether or not `squashing commits` is performed. The
operations are independent. However, when both `rebasing` and `squashing commits` are performed for all
changes to a repository the commit history is linear where each commit represents a new feature
or bug fix. Some projects require this type of [clean commit history](git-glossary.md#clean_commit_history)
and other projects do not.

Distrubuted source code control systems such as github have evloved to support cleaner commit histories. 
For example, github has implemented several options for merging pull requests that provide control
over `squashing commits` and `rebasing`. However, one can create cleaner commit histories locally.
[Here are instructions](cleanup_b4_pull_request.md) on how to accomplish `squashing commits` and `rebasing`
locally before creating a pull request rather than trying to accomplish these operations during the
merge of a pull request.
