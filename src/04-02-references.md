## References ##

You may have noticed the _very colorful_ labels in the GitX screenshot on the previous page. (If not, go back and have another peek. I'll wait.) Those labels are GitX's way of showing **references**.

I don't want to spend too much time talking about what each color means, because that particular representation is specific to GitX and you might be using something else. But however your visualizer represents them, you need to know what they are. (_Can I get a drumroll, please?_)

**References are pointers to commits.**

References come in several flavors: **local branch, remote branch**, and **tag**.

On disk, a ***local branch reference*** consists entirely of a file in your project's .git/refs/heads directory. This file contains the 40-byte identifier of the commit that the reference points to... and that's it. **The entire file is 40 bytes.**

You might have heard people talk about how Git allows "cheap branching." This is (part of) what they mean. Creating a branch in Git just means writing 40 bytes to disk, which is why `git branch foo` is so freaking fast.

What's **really** interesting about references, though, is how they behave. So, let's move on.
