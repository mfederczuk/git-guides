# 2.2.1 Merge Commits #

Previous: [Commit Messages](../messages.md),
 Up: [Commit Messages](../messages.md)
 &nbsp; \[[Contents](../../index.md)\]

Instead of using **Git**'s default commit messages for merging branches, merge
 commits should look like this:

	Merge in feature <feature name>

So when having a feature branch called "`feature/cool-new-thing`", the merge
 commit message could look something like this:

	Merge in feature cool new thing

The same applies to pull requests, instead of **GitHub**'s default message, the
 message should read:

	Merge in feature/fix/change <feature/fix/change name>

When merging a development or hotfix branch into the master branch the messages
 should just read:

	Release v<version name>

Since every commit on the master branch (except the initial commit) represents a
 new release.

The default messages reference the branches that get merged in, and these
 branches will probably be deleted in the future, which is why we don't use the
 default messages.  
This is more of a personal preference, it just bugs me that commit messages
 contain references to branches that do not exist anymore.  
Also, this gives contributors more freedom what to name their branches when
 forking the repository.
