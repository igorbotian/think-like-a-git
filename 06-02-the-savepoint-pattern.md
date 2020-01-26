## The Savepoint Pattern ##

Here's a quick overview of the steps in this recipe:

1. Make sure you're on the right branch and that you have a clean working state.
2. Create a new branch to use as a savepoint, but don't switch to it.
3. Do the merge.
4. Switch to your visualizer and predict how its view will change when you refresh it.
5. Refresh your visualizer and see whether your prediction was correct.
6. Are you happy with the result?
  If YES: Delete the savepoint.
  If NO: Reset your branch to the savepoint.
(Unless the last video game you ever played was Super Mario Brothers, it should be obvious why I call this one the Savepoint pattern.)

**THE LONG VERSION**

You're on the ***master*** branch and you want the changes from the ***spiffy_new_feature*** branch to be incorporated into ***master***. You're reasonably confident that you'll want to keep the changes, but you want to be able to abort it if, for example, this feature has unintended side effects.

1. **Make sure you're on the right branch and that you have a clean working state.**

2. Whatever visualizer you're using, figure out how it shows you where your current branch is. Or, at the command line, type `git status` and you should see something like this:
```
# On branch master
nothing to commit (working directory clean)
```
3. **Create a new branch to use as a savepoint, but don't switch to it.**  
Type `git branch savepoint`. Now, if you type `git status` again, you should still see a message that you're on the ***master*** branch.

4. **Do the merge.**  
  Type `git merge spiffy_new_feature`. If you're lucky, there won't be any merge conflicts you can't resolve.  
  **If you want to abort the merge** at this point, just type `git reset --hard`.

5. **Switch to your visualizer and predict how its view will change when you refresh it.**  
  For example:  
  **a.** After a merge, you should see a new commit.  
  **b.** The new commit should have a message like "Merge branch 'spiffy_new_feature' into master".  
  **c.** Your ***master*** branch label should have moved to this new commit, while the ***spiffy_new_feature*** branch label should still be in the same place.  

6. **Refresh your visualizer and see whether your prediction was correct.**

7. Are you happy with the result?  
  **If YES**: Delete the savepoint.
```
git branch -d savepoint
```
  **If NO**: Reset your branch to the savepoint.
```
git reset --hard savepoint
```

If you want to clean up, you can now delete the savepoint with `git branch -d savepoint`.
