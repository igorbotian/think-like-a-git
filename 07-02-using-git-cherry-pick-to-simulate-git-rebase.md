## Using 'git cherry-pick' to Simulate 'git rebase' ##

Once you have `git cherry-pick` down, you can start off by thinking of `git rebase` as being a faster way to cherry-pick all of the commits in a given branch at once, rather than having to type out their IDs separately.

_(That's only the very beginning of what rebase can do, but I'll write the rest of this section another time.)_

Let's go back to our trusty example, but this time add some branches...

![git rebase](before-rebase.png)

Now, I could type this sequence of commands:

```
git checkout foo
git checkout -b newbar
git cherry-pick C D E
```

In order, these commands:
- make sure we're at **H** (because 'foo' points to it),
- create **and check out** a temporary branch called "newbar", also pointing at **H**,
- apply the changes from **C**, **D**, and **E**, creating new commits **C'**, **D'**, and **E'**, and update the "newbar" branch so it points at **E'**.

Which would give me a repository that looked like this:

![git rebase midpoint](cherry-pick-qua-rebase-example-midpoint.png)

Then, I could type this:

```
git checkout bar
git reset --hard newbar
git branch -d newbar
```

Which would:
- Switch to the branch called "bar",
- Forcibly move the "bar" branch pointer so that it pointed to the same place as the "newbar" branch (and, thanks to the --hard flag, update my working directory to match the new location), and
- Delete the temporary "newbar" branch.

And leave my repository looking like this _(note that the original_ ***D*** _and_ ***E*** _nodes are no longer reachable, because no branch points to them):_

![git rebase endpoint](cherry-pick-qua-rebase-example-endpoint.png)

**Or**, I could have accomplished all that by typing this instead:

```
git rebase foo bar
```

In other words, 'git rebase' (in this form) is a shortcut that lets you pick up entire sections of a repository and move them somewhere else.
