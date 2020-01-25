## Branches as Savepoints ##

Because a Git branch is just a 40-byte file on disk, **it takes orders of magnitude more time for you to tell the computer to create a branch** (by typing `git branch foo`) **than for your computer to actually do it**.

And because branches are references, and (_say it with me now_) [References Make Commits Reachable](http://think-like-a-git.net/sections/experimenting-with-git/references-make-commits-reachable.html), **creating a branch is a way to "nail down" part of the graph** that you might want to come back to later.

And because neither `git merge` nor `git rebase` will change your existing commits ([remember](http://think-like-a-git.net/sections/graphs-and-git/garbage-collection.html), a commit's ID is a hash of its contents **and its history**), you can create a temporary branch any time you want to try something you're even just a little bit unsure about.

In other words, **creating a branch before you try a merge or a rebase is like saving your game before you battle the boss**.
