# Rebase From the Ground Up #

Git's `rebase` command was one of those things that it took me forever to figure out. This was partly because I just had a lot to learn about managing branches in general, but it was also partly because it seemed like the only time people bothered to write about rebase was to say [how incredibly weird and dangerous it was](http://think-like-a-git.net/sections/git-makes-more-sense-when-you-understand-x/example-4-lsd-and-chainsaws.html).

This is a damn shame, because **rebase is the single most useful command I use in Git**. More importantly, **it's actually pretty easy to understand once you get the hang of it**.

**DANGER, WILL ROBINSON!**

I've tried to demystify rebase in this section, and I do plan to write up a strategy for experimenting with rebase, just as I have with merge. However, I recently realized that I forgot to mention something very important about rebase: **it is generally considered rude to rewrite history in public!**

Before you start using rebase in a shared repository, make sure everyone who works on your project is comfortable working with rebase. You might also consider changing everyone's default pull strategy to "rebase" instead of "merge".

**END OF PUBLIC SERVICE ANNOUNCEMENT.**

With that said, I'm going to take a brief digression, because I think it's much easier to explain rebase in the context of another Git command: `git cherry-pick`.
