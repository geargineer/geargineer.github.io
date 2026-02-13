+++
date = '2026-02-11T18:55:10+01:00'
draft = true
title = 'How_to_create_a_hugo_site'
+++

# How to Create This Hugo Site

## Choose the Template
gohugo provides lot of templates, but most of them require a deep knowledge of how hugo works. So I looked for a minimal theme which can (more) easily be understood and so adapted to my needs.
After some research I found **hugo-bearblog** which turned out to be a good starting point.

## Clone the Example-Site
bearblog provides in its themes directory an example site - a very basic structure which you can copy to the statig-images and the content directory - I did so...

## Make some very basic edits to _index.md
My first step was (afer starting hugo server) to make some minor modifications to _index.md and see what happens: and - yes - the changes immediately showed up on the local site.

## Enable local previewing
When want to use a markdown-editor to have a WYSIWYG experience you have to use a "trick" so that images show also up in the editor.
Do that by setting a symlink within the content folder:
```
ln -s ../static/images/ ./images
```

 This symlinks the static image folder to your content folder. So if you reference an image using the local relative path "images" within content, the image will also be displayed by hugo server as it also resides in the static image folder.
To reference an image within the markdown use the following syntax:
```
![brompton_trento.jpg](images/brompton_trento.jpg)
```

Proof:
![brompton_trento.jpg](images/brompton_trento.jpg)

## Now let's adapt the global head
In the themes folder there is a subfolder **layouts/partials** . In this subfolder reside html-snippets ("partials") which will be referenced by name and reused every where needed/mentioned. So modifying the custom_head.html should add some additional (global) informaton to the site.
I added the following to custom_head.html:
```
<!-- A partial to be overwritten by the user.
  Simply place a custom_head.html into
  your local /layouts/partials-directory -->
<h1>The Geargineer</h1>
```

And yeah - there it is. But there is also a "bearblog"-block which I want to get rid of. But first let's add a image to the custom header and see what's happening:

![geargineer](images/front_matter_2.jpg)

** that works but is shown only on the index-page **


```
477  cat _index.md 
  478  vi _index.md 
  479  pwd
  480  ls -lrta
  481  pwd
  482  cd images/
  483  ls
  484  cd ..
  485  rmdir images/
  486  cd images/
  487  ls
  488  rm *
  489  cd ..
  490  rmdir images/
  491  ls
  492  ln -s ../static/images/ ./images
  493  ls -lrt
  494  cd Immanuel
  495  cd Geargineer_StaticSite/
  496  cd geargineer.github.io/
  497  ls
  498  hugo server
  502  cd Geargineer_StaticSite/
  503  cd geargineer.github.io/
  508  hugo new how_to_create_a_hugo_site.md
  509  pwd
  510  cd themes/
```


## First Try: modif _index.md

