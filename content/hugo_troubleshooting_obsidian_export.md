---
title: obsidian export corrupted
draft: "true"
tags:
  - hugosite
date: 2026-03-16T14:21:10.701Z
lastmod: 2026-03-15T18:41:09.000Z
---
# Hugo: troubleshooting obsidian export

## Current State

there is a successful export from obsidian in dev.geargineer/content and one corrupted in dev.geargineer.draft/content.\
CAUTION: obsidian content has changed between the corrupt/non-corrupt export!

### let's do a diff:

```
diff -bur ./git_tipps_and_tricks.md ../../dev.geargineer/content/git_tipps_and_tricks.md  
--- ./git_tipps_and_tricks.md   2026-03-15 19:04:52.436245367 +0100  
+++ ../../dev.geargineer/content/git_tipps_and_tricks.md        2026-03-15 19:04:24.790891502 +0100  
@@ -1,5 +1,5 @@  
---  
-date: '2026-03-15 19:04:52'  
+date: '2026-03-08 20:00:51'  
draft: 'true'  
tags:  
- git  
diff -bur ./hugo_fixing_lugo_theme.md ../../dev.geargineer/content/hugo_fixing_lugo_theme.md  
--- ./hugo_fixing_lugo_theme.md 2026-03-15 19:04:52.437349993 +0100  
+++ ../../dev.geargineer/content/hugo_fixing_lugo_theme.md      2026-03-15 19:03:46.391234452 +0100  
@@ -1,5 +1,5 @@  
---  
-date: '2026-03-15 19:04:52'  
+date: '2026-03-15 19:03:46'  
draft: 'true'  
tags:  
- hugosite  
diff -bur ./hugo_list_pages_missing.md ../../dev.geargineer/content/hugo_list_pages_missing.md  
--- ./hugo_list_pages_missing.md        2026-03-15 19:04:52.436907960 +0100  
+++ ../../dev.geargineer/content/hugo_list_pages_missing.md     2026-03-15 19:04:24.791006289 +0100  
@@ -1,5 +1,5 @@  
---  
-date: '2026-03-15 19:04:52'  
+date: '2026-03-08 20:00:51'  
---  
   
# Problem:  
diff -bur ./hugo_nil_pointer.md ../../dev.geargineer/content/hugo_nil_pointer.md  
--- ./hugo_nil_pointer.md       2026-03-15 19:04:52.436831823 +0100  
+++ ../../dev.geargineer/content/hugo_nil_pointer.md    2026-03-15 19:04:24.791119752 +0100  
@@ -1,5 +1,5 @@  
---  
-date: '2026-03-15 19:04:52'  
+date: '2026-03-08 20:00:51'  
draft: 'true'  
title: Hugo compile crashes with error  
---  
@@ -8,8 +8,6 @@  
   
![[Pasted image 20260308190702.png]]  
   
-Image reference in hugo-syntax:  
-  
## Solution:  
   
see: https://discourse.gohugo.io/t/error-calling-translationbasename-runtime-error-invalid-memory-ad  
dress-or-nil-pointer-dereference/49836  
diff -bur ./hugo_obsidian_frontmatter.md ../../dev.geargineer/content/hugo_obsidian_frontmatter.md  
--- ./hugo_obsidian_frontmatter.md      2026-03-15 19:04:52.436985615 +0100  
+++ ../../dev.geargineer/content/hugo_obsidian_frontmatter.md   2026-03-15 19:04:24.791246721 +0100  
@@ -1,5 +1,5 @@  
---  
-date: '2026-03-15 19:04:52'  
+date: '2026-03-08 20:00:51'  
title: Setting hugo frontmatter in obsidian  
---  
   
Nur in ../../dev.geargineer/content: hugopage.md.  
diff -bur ./hugo_publish.md ../../dev.geargineer/content/hugo_publish.md  
--- ./hugo_publish.md   2026-03-15 19:04:52.436112106 +0100  
+++ ../../dev.geargineer/content/hugo_publish.md        2026-03-15 19:04:24.791366384 +0100  
@@ -1,5 +1,5 @@  
---  
-date: '2026-03-15 19:04:52'  
+date: '2026-03-08 20:00:51'  
title: Hugo Publish Extension for Obsidian  
---  
   
diff -bur ./hugo_theme.md ../../dev.geargineer/content/hugo_theme.md  
--- ./hugo_theme.md     2026-03-15 19:04:52.436490220 +0100  
+++ ../../dev.geargineer/content/hugo_theme.md  2026-03-15 19:04:24.791482321 +0100  
@@ -1,5 +1,5 @@  
---  
-date: '2026-03-15 19:04:52'  
+date: '2026-03-08 20:00:51'  
title: Hugo Themes  
---  
   
diff -bur ./_index.md ../../dev.geargineer/content/_index.md  
--- ./_index.md 2026-03-15 19:04:52.437458409 +0100  
+++ ../../dev.geargineer/content/_index.md      2026-03-15 19:04:24.790762920 +0100  
@@ -1,8 +1,8 @@  
---  
cascade:  
  type: docs  
-created: 2026-03-15 19:04:52.283466  
-date: '2026-03-15 19:04:52'  
+created: 2026-03-08 20:00:51.025065  
+date: '2026-03-08 20:00:51'  
menu:  
  main:  
    title: Notes  
diff -bur ./obsidian_cms.md ../../dev.geargineer/content/obsidian_cms.md  
--- ./obsidian_cms.md   2026-03-15 19:04:52.436659345 +0100  
+++ ../../dev.geargineer/content/obsidian_cms.md        2026-03-15 19:04:24.791679080 +0100  
@@ -1,5 +1,5 @@  
---  
-date: '2026-03-15 19:04:52'  
+date: '2026-03-08 20:00:51'  
title: Obsidian as CMS for Hugo  
---  
   
diff -bur ./obsidian_to_hugo.md ../../dev.geargineer/content/obsidian_to_hugo.md  
--- ./obsidian_to_hugo.md       2026-03-15 19:04:52.436744238 +0100  
+++ ../../dev.geargineer/content/obsidian_to_hugo.md    2026-03-15 19:04:24.791791678 +0100  
@@ -1,5 +1,5 @@  
---  
-date: '2026-03-15 19:04:52'  
+date: '2026-03-08 20:00:51'  
---  
   
draft:true  
diff -bur ./publishing_hugo_sagar_se.md ../../dev.geargineer/content/publishing_hugo_sagar_se.md  
--- ./publishing_hugo_sagar_se.md       2026-03-15 19:04:52.435963816 +0100  
+++ ../../dev.geargineer/content/publishing_hugo_sagar_se.md    2026-03-15 19:04:24.791907829 +0100  
@@ -1,5 +1,5 @@  
---  
-date: '2026-03-15 19:04:52'  
+date: '2026-03-08 20:00:51'  
---  
   
#hugosite    
diff -bur ./structuring_projects.md ../../dev.geargineer/content/structuring_projects.md  
--- ./structuring_projects.md   2026-03-15 19:04:52.437149036 +0100  
+++ ../../dev.geargineer/content/structuring_projects.md        2026-03-15 19:04:24.792018934 +0100  
@@ -1,5 +1,5 @@  
---  
-date: '2026-03-15 19:04:52'  
+date: '2026-03-08 20:00:51'  
title: Structuring Projects  
---  
   
diff -bur ./thinkstuff.md ../../dev.geargineer/content/thinkstuff.md  
--- ./thinkstuff.md     2026-03-15 19:04:52.435821593 +0100  
+++ ../../dev.geargineer/content/thinkstuff.md  2026-03-15 19:04:24.792125392 +0100  
@@ -1,5 +1,5 @@  
---  
-date: '2026-03-15 19:04:52'  
+date: '2026-03-08 20:00:51'  
---  
   
# What to Print on Your T-Shirt?
```
