## Garbage Collection ##

Imagine this scenario: you write some code and check it in. Then, you realize you forgot to run the tests, so you run them, and they uncover a syntax error. Or you spot a typo. For whatever reason, you weren't done when you thought you were done.

Back when I used Subversion, the only thing to be done about this was to add the new change in another commit. Often, I'd wind up with three or four versions in my history. The first one would say "add feature X", and the next several would have messages like "oops, found typo" or "bugfix" or "forgot to run tests".

Git gives you another option: you can tack the new change on to the previous commit using `git commit --amend`. This keeps all of your related changes bundled together in one commit, so you can understand it more quickly when you're reviewing it later.

Here's another interesting fact about Git commits: a commit's ID is a [SHA-1 hash](http://en.wikipedia.org/wiki/SHA-1) of several pieces of information: the contents of the commit, **and the IDs of its parent commits**.

Which means that, when you use `git commit --amend`, you're actually building a completely different commit, and pointing your local branch reference to it instead. **The first commit you made is still there on disk, and you can still get back to it** (more on this later). However, in the interest of not cluttering up your view, neither `git log` nor your Git visualizer will show it to you, because it's not part of the history of something [Git thinks] you care about.

Eventually, Git will decide that it's time to run [garbage collection](http://en.wikipedia.org/wiki/Garbage_collection_(computer_science)#Reachability_of_an_object). (You can trigger this process yourself, using `git gc`.) Starting from every branch and every tag, Git walks back through the graph, building a list of every commit it can reach. Once it's reached the end of every path, it deletes all the commits it didn't visit.
