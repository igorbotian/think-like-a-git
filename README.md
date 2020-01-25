# Think like (a) Git

Contents of [think-like-a-git.net](http://www.think-like-a-git.net) site in Markdown format.

## Making an e-book

The Markdown file can be easily converted to an e-book format.  
An example of making an EPUB book by means of [Pandoc utility](https://pandoc.org/) is below:

```bash
pandoc src/*.md -f markdown -t epub -s -o think-like-a-git.epub
```