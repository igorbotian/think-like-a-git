# Testing Out Merges #

These days, I sling branches around without really thinking much about it. But the first few times I tried using different branches to develop features, it was a bit nerve-wracking. If that's where you are, what follows are two simple recipes that should help you play around with `git merge` until you understand exactly what it does.

I've put together two slight variations on the same operation. Both techniques basically do the same thing, but one of them relies on a slightly scarier-sounding Git command for the undo.

You might prefer one or the other based on how uncertain you are — about either your Git skills, or the specific merge you're about to try.

- Use the [Scout pattern](http://think-like-a-git.net/sections/testing-out-merges/the-scout-pattern.html) if you're still unclear on exactly what `git merge` does, or if you think it's likely that you'll decide to back out of the merge.
- Use the [Savepoint pattern](http://think-like-a-git.net/sections/testing-out-merges/the-savepoint-pattern.html) if you're pretty sure what you want to do, but just want to leave yourself an undo button in case things get too messy.
