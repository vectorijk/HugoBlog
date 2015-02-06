---
date: "2015-02-02T07:25:03-08:00"
title: "Build My Blog with Hugo"
description: "First Post"
categories: 
  - "blog"
  - "Hugo"
---

## Hello Hugo

[Hugo](http://gohugo.io) is a static site generator written in [Go](http://www.golang.org). It is awesome. Compared to [jekyll](http://jekyllrb.com) or other static site generator, it is light-weight. 

## How it's made

There is a [quick tutorial](http://gohugo.io/overview/quickstart/) teach yourself how to deploy and generator with [Hugo](http://gohugo.io).

UCSB Philosophy website is also build with [Hugo](http://gohugo.io). This [README](https://github.com/ucsbphil/philweb/blob/master/README.md) on its Github.com is also a good introdution.

### Test on localhost

Install Hugo, then run it from the command-line:

```
hugo server --source=/path/to/project/folder --watch
```

Every change when you save file, whole site will be generated again and refresh the browser. So you could see the changes immediately. 

When you done with your test on localhost, run 
```
hugo --source=/path/to/project/folder/
```
hugo will generate static web and substitute `localhost:1313` with `baseurl` into your `config.(yaml|toml|json)` if it's set up.

### config.(yaml|toml|json)

```
---
contentdir: "content"
layoutdir: "layouts"
publishdir: "public"
indexes:
  category: "categories"
baseurl : "http://web.cecs.pdx.edu/~jiangkai"
languageCode : "en-us"
title : "vectorijk"
canonifyurls : true
...
```

`canonifyurls` is true, hugo will change `localhost:1313` with `baseurl` ; else will not.

## What's next

Copy `public` directory into your web server directory (like `public_html`). Okay, it's done.

### TODO
Write a `Makefiles`

