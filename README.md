# Think like (a) Git
![EPUB](https://github.com/igorbotian/think-like-a-git/workflows/EPUB/badge.svg)

Contents of [think-like-a-git.net](http://www.think-like-a-git.net) site in Markdown format.

## How to build

The Markdown file can be easily converted to an e-book format.  
An example of building an EPUB book by means of [Pandoc utility](https://pandoc.org/) (v2.0 or above) is below:

```bash
pandoc src/*.md --resource-path=.:src -f markdown -t epub -s -o think-like-a-git.epub
```

## Download

The `.epub` and `.mobi` files can be found [here](https://github.com/igorbotian/think-like-a-git/releases/latest).
