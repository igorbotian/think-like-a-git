## Black Belt Merging ##

Once you're comfortable with the Savepoint pattern, you might get tired of creating the savepoint branch, only to have to remember to delete it every time. If so, I have good news for you: you don't actually need to use a branch as a savepoint for merges.

Merge commits always wind up with a branch label pointing at them, and one of the branch's parent commits will be the commit that that branch label was just moved from.

It may take you a few tries to parse that sentence. The upshot is that the commit you started on — the one you would've marked with a savepoint branch — **will always be reachable**.

Here's the thing: **Git doesn't care what you call your branches**. Remember, branches are just a 40-byte file on disk that points to the commit's SHA-1 hash, which is what Git really uses for all of its work. The branch is just there for us puny humans to have some convenient, memorable name pointing to part of the graph.

At the end of [the Savepoint pattern](http://think-like-a-git.net/sections/testing-out-merges/the-savepoint-pattern.html), the command you type to reset your branch to the savepoint is `git reset --hard` savepoint (where "savepoint" is a branch name). If you look at the documentation that comes up when you type `git reset -h`, you'll see that the final argument it takes is called `<commit>`. Older versions of the documentation called this `<commit-ish>`, which was a convenient reminder that you could use anything that Git can turn into a SHA-1 hash.

Things Git is happy to accept in a `<commit>` argument include (but are probably not limited to):
- Branch names
- Tags
- Relative references like **HEAD\^**, **HEAD\^\^**, or **HEAD~3**
- partial SHA-1 hashes like 8d434382 (you just have to provide enough initial digits to be unique; Git will fill in the rest for you)
- SHA-1 hashes like 8d434382d9420940be260199a8a058cf468d9037 (these are _very easy_ for Git to turn into SHA-1 hashes!)

So, at the end of [the Savepoint pattern](http://think-like-a-git.net/sections/testing-out-merges/the-savepoint-pattern.html), if you wanted to back out of the merge, you could just as easily use `git log` or your visualizer to find the SHA-1 of the commit (let's say it starts with 1234abcd), and type this:

```
git reset --hard 1234abcd
```

...and **Git would behave exactly the same** as if you'd remembered to create a branch in the first place.

> That bit about "if you'd remembered to" reminds me: one of the single most helpful bits of commentary I ever read about Git was Ryan Tomayko's [The Thing About Git](http://tomayko.com/writings/the-thing-about-git). (Yes, that's the same thing I linked to in [LSD and Chainsaws](http://think-like-a-git.net/sections/git-makes-more-sense-when-you-understand-x/example-4-lsd-and-chainsaws.html).)
