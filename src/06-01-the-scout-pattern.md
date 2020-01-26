## The Scout Pattern ##

Here's a quick overview of the steps in this recipe:

1. Make sure you're on the right branch and that you have a clean working state.
2. Create a new branch (I often name it _test_merge_) and switch to it.
3. Do the merge.
4. Switch to your visualizer and predict how its view will change when you refresh it.
5. Refresh your visualizer and see whether your prediction was correct.
6. Are you happy with the result?
  - If YES: Move your real branch forward to where the _test_merge_ branch is.
  - If NO: Delete the _test_merge_ branch.

I call this the Scout pattern: you're unsure what the terrain ahead is like, so you send a scouting party ahead to check it out. If they radio back that everything's okay, you'll move ahead and join them. If not, well, it was just a small scouting party and we'll tell the families that they died with honor...

**THE LONG VERSION**

You're on the ***master*** branch and you want the changes from the ***spiffy_new_feature*** branch to be incorporated into ***master***. You're not sure if this will be a good idea, so you want to try out the merge, but be able to abort it if things don't go smoothly.

1. **Make sure you're on the right branch and that you have a clean working state.**  
  Whatever visualizer you're using, figure out how it shows you where your current branch is. Or, at the command line, type `git status` and you should see something like this:
```
# On branch master
nothing to commit (working directory clean)
```

2. **Create a new branch and switch to it.**  
  Type `git checkout -b test_merge`. Now, if you type `git status` again, you should see a message that you're on the ***test_merge*** branch.

3. Do the merge.  
  Type `git merge spiffy_new_feature`. If you're lucky, there won't be any merge conflicts you can't resolve.  
  **If you want to abort the merge** at this point, type `git reset --hard`.

4. **Switch to your visualizer and predict how its view will change when you refresh it.**  
  For example:  
    **a.** After a merge, you should see a new commit.  
    **b.** The new commit should have a message like "Merge branch 'spiffy_new_feature' into test_merge".  
    **c.** Your ***test_merge*** branch label should have moved to this new commit, while the ***master*** and ***spiffy_new_feature*** branch labels should still be in the same place.  

5. **Refresh your visualizer and see whether your prediction was correct.**

6. **Are you happy with the result?**  
  **If YES**: Move the _master_ branch forward to where the _test_merge_ branch is with:
```
git checkout master
git merge test_merge
```
  **If NO**: Drop the _test_merge_ branch with:
```
git checkout master
git branch -D test_merge
```
