## The Reference Reference ##

As previously mentioned, there are a few different kinds of references, and they all point to commits in your repository. The only difference between them is how and when they move. (When I say that a reference moves, I mean that the ID of the commit that it points to is updated.)

**Local branch references** are specific to a single repository: your local one. Commands that affect local branch references include `commit`, `merge`, `rebase`, and `reset`.

**Remote branch references** are also specific to a single repository, but one that's previously been defined as a remote. Commands that affect remote branch references include `fetch` and `push`.

_(The `pull` command is a special case: it combines `fetch` and either a `merge` or a `rebase`, depending on how you've got Git configured.)_

**Tag references** are basically like branch references that never move. **Once you've created a tag, it will never change** (unless you explicitly update it using the `--force` option). This behavior makes them useful for marking specific versions of a software package, or marking exactly what got deployed to a production server on a particular date. As of this writing, I only know of one command that affects tags. As you might guess, it's `tag`.
