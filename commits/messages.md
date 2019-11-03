<!-- markdownlint-disable MD046 -->

# 2.2 Commit Messages #

Previous: [Commit Contents](./contents.md),
 Up: [Commits](../commits.md)
 &nbsp; \[[Contents](../index.md)\]

There are some well established conventions for **Git** messages. A good summary
 of them can be found [here](https://chris.beams.io/posts/git-commit).

* The subject line should be capitalized (like in a sentence)
* The subject line should not exceed 50 characters
* Use the imperative mood in the subject line
* The subject line should not end with a period
* The subject line should be a short description of the changes
* Separate the subject line from the message body with an empty line
* Wrap the message body after 72 characters
* The message body should primarely be used to explain WHAT changed and WHY this
   change was necessary instead of HOW the change was implemented

It's also best practice to use an actual editor instead of the `-m` option.  
The commit message editor can be changed by using:

```sh
git config --global core.editor "<your editor here>"
```

A message should not be *just* a reference to an issue that gets fixed,
 i.e.: don't do this:

	Fix issue #123

The message should still describe what got fixed and should just reference the
 issue that gets resolved at the end of the body.

	Fix this and that problem

	Closes issue #123.

A lengthy description of what changed and why the change was made is not
 necessary since the referenced issue will already have described why the
 problem needs to be fixed.

* [Merge Commits](./messages/merge-commits.md): &nbsp; How to write merge commit
                                                        messages
