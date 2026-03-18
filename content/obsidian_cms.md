---
title: Obsidian as CMS for Hugo
draft: "true"
tags:
  - hugosite
  - obsidian
date: 2026-02-28T07:00:05.662Z
lastmod: 2026-03-18T10:13:42.932Z
---
# What CMS to use?

Hugo and CMS - sounds like nonsense as hugo uses simply plan markdown?

## Alternative 1: plain markdown

No image preview.\
Plain text editor\
No copy-paste for images

## Alternative 2: markdown editor with preview

Use one that

* follows symlinks (allows inclusion of images from image-dir)

## Alternative 3: use Obsidian

Obsidian relies on markdown files (good)\
.. has a special syntax (not so good)\
but there is a plugin "publish to hugo" (very good)\
.. allows copy paste of images (very good)

#### Setting frontmatter in obsidian

Setting frontmatter (metadata) in obsidian is directly supported. Simply type in the first line (under the page title) three dashes: "---"\
Obsidian recognizes that you want to enter structure frontmatter and starts a table, where you can enter key-value pairs:\
![Pasted image 20260318111340.png](/ob/Pasted%20image%2020260318111340.png)

# Hugo Publish

See: https://github.com/kirito41dd/obsidian-hugo-publish

*the following descriptions is copied from the extension's repo*, license see: https://www.apache.org/licenses/LICENSE-2.0

***

This plugin helps you publish hugo blog through obsidian.

## Features

This plugin will convert the `.md` file and related images in obsidian to the hugo site dir.\
Conversion includes:

* `[[link.com]]` -> `[link.com](link.com)`
* `[[link.com|alias-text]]` -> `[alias-text](link.com)`
* `![[xxx.png]]` -> `![xxx.png](/${static_dir}/xx.png)`
* `![[xxx.png|200*100]]` -> `![xxx.png](/${static_dir}/xx.png)`
* Auto write md's yaml header like: title,date,lastmod

## How to use

1. Complete the plugin settings: `blog_tag`,`hugo_site`...
2. Set `tags` in obsidian's md as `${blog_tag}`
3. Click `hugo sync` button or run cmd `Hugo Publish: Sync blog`
4. Enter the hugo site dir to run `hugo server` to check it

### Here my configuration of the plugin

I am writing every obsidian-markdown "plain" into hugo's content directory:

![Pasted image 20260318111105.png](/ob/Pasted%20image%2020260318111105.png)
