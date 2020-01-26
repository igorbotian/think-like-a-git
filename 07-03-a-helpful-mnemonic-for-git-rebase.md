## A Helpful Mnemonic for 'git rebase' Arguments ##

To summarize the previous section, this:

```
git checkout foo
git checkout -b newbar
git cherry-pick C D E
git checkout bar
git reset --hard newbar
git branch -d newbar
```

is equivalent to this:

```
git rebase foo bar
```

When you do a rebase, you are ***rewriting history***. You are, in effect, saying to Git, "Hey, you know those things that happened over there on that completely different timeline? I want you to pretend that they happened here instead."

The documentation for the rebase command lists a lot of different ways you can invoke it. Frankly, I'm still not sure what some of them do, and I have a hard time parsing out the different parentheses and brackets to figure out exactly how you'd use, for example, `--onto`.

Here's how I think of it: in English, we read **from left to right**. On most charts that show the change in something over time, time is shown on the x-axis of the graph, with time increasing from left to right. When you issue commands to the shell, you can put several of them on one line, and they'll be executed in order **from left to right**.

So when I use `git rebase`, I (_almost_) always give it two arguments: the name of the place I want to start from, and the name of the place I want to end up. Or, to put it another way, I tell rebase the sequence of events I want it to create, **from left to right**: `git rebase first_this then_this`
