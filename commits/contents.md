# 2.1 Commit Contents #

Previous: [Commits](../commits.md),
 Up: [Commits](../commits.md)
 &nbsp; \[[Contents](../index.md)\]

One commit should only be a single logical change, like fixing a bug or changing
 formatting.  
This means that changes may also span several files.  
Changes to documentation, based on the changed code (e.g.: API references,
 changelog files, ...), can also be incorporated into the commit.

Big feature additions are best split into several commits on their own branch,
 and then merged back into the development branch.

Version numbers and version dates should be changed in a separate commit.

Committed code should also **always** be valid, meaning that the syntax is
 correct and, if it is a compiled language, the code needs to be able to compile
 without errors. **Never commit broken code!**  
Make sure to test what you wrote, runtime errors should be kept to a minimum.
 At best, that minimum should be zero.
