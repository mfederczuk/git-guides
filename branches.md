# 3 Branches #

Previous: [Commits](./commits.md),
 Up: [Top](./index.md)
 &nbsp; \[[Contents](./index.md)\]

This branching system is based off of
 [Vincent Driessen's "A successful Git branching model"][a-successful-git-branching-model].

[a-successful-git-branching-model]: https://nvie.com/posts/a-successful-git-branching-model "A successful Git branching model &raquo; nvie.com"

## The master branch ##

The master branch is named, just like anywhere else "`master`".  
This branch tracks the initial commit and all release builds of the project.  
The lifespan of it is permanent, it will never be deleted.

Every commit in master branches (except the initial commit) represents a new
 release. All of these commits should also be merge commits and they should also
 be tagged with the version name.  

It's sometimes useful to refer to the initial commit of a branch, specifically
 the master branch. Sadly, there is so quick and easy way to refer to the
 initial commit.  
This is why the master branch can have a tag that point towards the initial
 commit, called "`TAIL`".  
If for whatever reason, there is more than one initial commit in the repository
 (branches with no unrelated histories), then the tags should have an underscore
 and the name of the branch as a suffix.
 (e.g.: `TAIL_master`, `TAIL_new-master`, `TAIL_docs`, ...)

A typical master branch could look something like this:

	* (tag: v2.1.0, master) Release v2.1.0
	|
	* (tag: v2.0.0) Release v2.0.0
	|
	* (tag: v1.0.1) Release v1.0.1
	|
	* (tag: v1.0.0) Release v1.0.0
	|
	* (tag: v0.1.0) Release v0.1.0
	|
	* (tag: TAIL) Initial commit

## The development branch ##

The branch "`develop`" tracks the development build of the project.  
It branches off of the initial commit and merges back into `master` for every
 new release.  
Like the master branch, the development branch, generally, has a permanent
 lifespan, though, it may be deleted if the project gets archived and is not
 under development anymore.

A `develop` branch could look like this:

	* (develop) Create some more stuff
	|
	* Bump up version number
	|
	* Update changelog file
	|
	* Fix baz
	|
	* Do some other stuff
	|
	* Create bar
	|
	* Create this thing
	|
	* Do foo
	|
	* Add the thing
	|
	* Initial commit

## The feature, change and fix branches ##

Feature, change and fix branches are used to create new additions, change
 existing behavior and fix problems, respectively.  
The names of these branches must only contain ASCII letters, dashes and
 underscores. **`[A-Za-z-_]+`**  
They must also have the prefix "`feature/`", "`change/`" or "`fix/`" (dependent
 on what branch they are).  
They branch off of and merge back into `develop`. After merging, they should be
 deleted.

Feature, change and fix branches may span several versions of the project.  
For example: Just because a feature branch split of at version `1.0.0`, doesn't
 mean that the feature must be completed and merge back into `develop` before
 version `1.1.0`.

Change and fix branches are generally only seen when creating pull requests.  
For collaborators that have read-write access to a repository, change and fix
 are branches completely optional and it is even discouraged to use them, since
 they only create unnecessary branches.

Feature branches might look something like this:

	* (feature/cool-new-thing) Fix some problems
	|
	* Finish up this feature
	|
	* Clean up that stuff
	|
	* Add that file
	|
	* Add this file

## The hotfix branches ##

Hotfix branches track important patches of the projects.  
The same naming rules that feature, change and fix branches have apply to hotfix
 branches. The only differences is that hotfix branches use the "`hotfix/`"
 prefix instead.  
These branches split off of the master branch and merge back into `master` and
 also into `develop`.  
After merging, the branches should be deleted.

Hotfix branches contain most of the time very few commits:

	* (hotfix/important-fix) Bump up version number
	|
	* Fix this thing

## Example ##

This is a very basic example of how a branch network could look like with this
 branching system:

	master   hotfix/...   develop   feature/...
	  |
	  |                      |
	  |\ ____     __________/|
	  |       \ /            |
	  |        |             |
	  |  _____/              |\______
	  |/                     |        \
	  |                      |         |
	  |                      |         |
	  |                      |         |
	  |                      |  ______/
	  |                      |/
	  |                      |
	  |                      |
	  |  ___________________/
	  |/
	  |
