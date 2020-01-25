## Reachability ##

**You can think of this graph as a set of three parallel universes** with time flowing from left to right, so that A is the beginning of recorded history. _(The arrow represents the "follows" or "is subsequent to" relationship, so you might say that "B follows A".)_

![To see an ASCII version of this graph, type `git rebase --help`](reachability-example.png)

If you start from **E**, the history you'll see is **A**, **B**, **C**, **D**, **E**.

If you start from **H**, the history you'll see is **A**, **B**, **F**, **G**, **H**.

If you start from **K**, the history you'll see is **A**, **B**, **C**, **I**, **J**, **K**.

But the really important thing about this is that no matter which node you start with, **some parts of the graph will be unreachable to you**.

That sounds kind of pessimistic, so I'll turn it around: **Depending on where you start, you can reach parts of the graph that you couldn't get to otherwise**.

This may not sound like much, but stay with me for a little while longer—it's huge.
