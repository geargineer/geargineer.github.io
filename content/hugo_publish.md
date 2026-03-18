---
title: Hugo Publish Extension for Obsidian
date: 2026-02-28T07:04:48.365Z
lastmod: 2026-03-07T19:22:35.963Z
---
\#obsidian\_cms\
\#hugo\_site\
use tags without underscore\
\#obsidian\
\#hugosite

# How to set up Hugo Publish Extension

## Prerequisites

To start with the hugo-publis-extension on obsidian, I prepared the following:

* an obsidian vault with markdown files which will serve as CMS where I will write content, insert images and so on
* a local directory which is initialized as hugo-site containing a raw structure for hugo, in my case: \*/home/geargineer/Hugo\_Sites/geargineer.pages.io

## Configure obsidian plugin

Set configuration of hugo-extension to point to the local hugo-dir:\
![Pasted image 20260228081018.png](/ob/Pasted%20image%2020260228081018.png)\
(this also being the first image I try to share using hugo sync in obisidian)

\*\*pressing "hugo sync"\
... and it worked!!:\
![Pasted image 20260228081526.png](/ob/Pasted%20image%2020260228081526.png)

(ignore the "group intothebridge"). All markdowns are there.

## Front matter

Let's check the front matter:\
![Pasted image 20260228081651.png](/ob/Pasted%20image%2020260228081651.png)

hugo publish inserts automatically the front matter above (yaml-Syntax). Let's set this page "draft" directly in the content dir and see what happens on the next sync:

### Draft status
