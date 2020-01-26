# Experimenting With Git #

I said something really important on the previous page. It's so important I'll repeat it.

In describing Git's garbage collection algorithm, I said, "**Starting from every branch and every tag**, Git walks back through the graph, building a list of every commit it can reach." (_Emphasis added._)

Everything I've written up to this point has been to provide the background for you to **understand this one thing**. If I had ten seconds to tell you The Secret Of Git — _the entire point of this site_ — I can fit it into these four words:

**References make commits reachable.**
