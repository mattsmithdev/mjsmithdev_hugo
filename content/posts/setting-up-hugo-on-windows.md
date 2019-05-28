+++
categories = ["hugo"]
date = "2019-05-28T12:38:50-04:00"
description = ""
featured_image = "https://source.unsplash.com/collection/1459961/800x400/daily"
tags = ["hugo"]
title = "Setting Up Hugo on Windows"

+++
Two steps we want to accomplish here. Get Hugo installed on your Windows machine and add a theme. We'll work on deploy and hosting later.

## Installing Hugo on Windows

From the [Hugo Install Page](https://gohugo.io/getting-started/installing/#chocolatey-windows)...

Are you using Chocolatey (if not, you should be)? Then it's simple...

`choco install hugo -confirm`

Not using Chocolatey? Get the latest 32/64bit exe release zip from the [Hugo Github repository](https://github.com/gohugoio/hugo/releases). Hugo is a standalone exe with no installer. Just extract it where you would like to use it.

_Side Note:_ There is a 'Hugo Extended' release. Download this version if you need Sass css compiling for your theme, otherwise stick with the standard release. It doesn't hurt to use the extended, but it's not necessary for regular css.

## Create a New Hugo Project

You can use the downloaded Hugo exe from above to create a new project/site. From [Hugo's Quick Start](https://gohugo.io/getting-started/quick-start/) page...

1. Open up a command prompt (can be cmd, powershell, etc).
2. Change to the directory with the Hugo exe
3. Enter...  
   `hugo new site my_project_name`
4. Then change into the theme directory...  
   `cd my_project_name\themes`
5. Clone the theme's code from their repository, for example here's KeepIt's repositiory...
   `git clone https://github.com/Fastbyte01/KeepIt.git`

## Setting Up a Theme for Hugo

Hugo uses Themes for the design of the page, similar to Wordpress and other setups. There a list of free themes on [Hugo's Theme](https://themes.gohugo.io/) page.

Select a theme from the Hugo theme page. For example, [KeepIt](https://themes.gohugo.io/keepit/).

1. In the command prompt and Hugo directory from above, change to the  theme's directory...
   `cd my_project_name\themes`
2. Clone the theme's code from their repository, for example here's KeepIt's repositiory...
   `git clone https://github.com/Fastbyte01/KeepIt.git`

## Creating Content in Hugo

Hugo, like many static-site generators uses Markdown as its language of choice. You can use the Hugo exe to generate new pages. You can also just create them in Notepad or wherever and save it in the right directory. There are CMS setups, like [Forestry.io](https://forestry.io/) that tie into your setup and let you create pages like you would on Wordpress with a standard editor.

For right now we'll just use the Hugo exe to setup a new draft page for us to test with...
`hugo new posts/my-first-post.md`
...That will create a new draft (non-published) post without any content. If you look at the file under the posts directory in Notepad, you'll see the top of it has some meta information about the post...
```
---
title: "My First Post"
date: 2019-05-28T13:19:36-04:00
draft: true
---
```
...Since Hugo doesn't use a database, the meta information about your posts is stored at the top of the file surrounded by --- tags. We'll get more into this later.

## Testing Hugo Locally

Now you have Hugo installed, a theme setup, and even a first post. Yes, right now they're all just default, but let's just test it in a browser anyway. The Hugo exe includes a web server for local testing as part of it. So to fire it up using the drafts switch so we see our test draft post...

`hugo server -D`

...By default that will start the server at the following address...
[http://localhost:1313/](http://localhost:1313/). Go to that in your browser and you'll see your new Hugo site (hopefully)!

We'll get into customizing the theme and adding more articles in future blog posts. Welcome to Hugo!
