## My Humble Beginnings ##

When I first started using Git, I was really paranoid about losing code. The only VCS I'd used before that was Subversion, where branching is this arcane thing that causes all kinds of trouble. So I didn't have a lot of practice with merging -- let alone rebasing, which everyone said was really dangerous. (Remember [LSD and chainsaws?](http://think-like-a-git.net/sections/git-makes-more-sense-when-you-understand-x/example-4-lsd-and-chainsaws.html))

So, before I tried something I was a little uncertain about, **I would back up the entire directory**.

```
$ cd ..
$ cp -r work backup_work
$ cd work
```

Then I'd do the merge, or rebase, or whatever it was that I thought was tricky. If it looked like it worked, I'd continue on; if not, I'd delete the working directory, rename the old one, and try something else.

I don't have records, but I'm pretty sure **I did this for at least my first year of working with Git**.

When I finally realized that [references make commits reachable](http://think-like-a-git.net/sections/experimenting-with-git/references-make-commits-reachable.html), I (a) felt very dumb for all those times I backed up the repository, and (b) developed a much faster strategy for getting my repository back to a known state.
