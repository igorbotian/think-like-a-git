# Think like (a) Git
![EPUB](https://github.com/igorbotian/think-like-a-git/workflows/EPUB/badge.svg)

Contents of [think-like-a-git.net](http://www.think-like-a-git.net) site in Markdown format.

## Making an e-book

The Markdown file can be easily converted to an e-book format.  
An example of making an EPUB book by means of [Pandoc utility](https://pandoc.org/) is below:

```bash
pandoc *.md -f markdown -t epub -s -o think-like-a-git.epub
```