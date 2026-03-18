---
title: Hugo fixing the lugo theme
tags:
  - hugosite
  - hugotheme
draft: "true"
date: 2026-03-16T14:21:10.671Z
lastmod: 2026-03-15T18:00:48.000Z
---
# Fixing the lugo-theme

The lugo theme (as given by Luke Smith on github) seems to have two problems, which I (empirically) fixed as follows:

```
diff -bur lugo-master/layouts/_default/list.html ../dev.geargineer/themes/lugo/layouts/_default/list.html  
--- lugo-master/layouts/_default/list.html      2025-02-28 12:55:01.000000000 +0100  
+++ ../dev.geargineer/themes/lugo/layouts/_default/list.html    2026-03-15 17:26:33.000000000 +0100  
@@ -7,7 +7,7 @@  
{{- range.Pages }}  
<li>  
       {{- if .Param "datesinlist" }}<time datetime="{{ .Date.Format "2006-01-02T15:04:05Z07:00" }}">{{ .Date.Format "2006 Jan 02" }}</time> &ndash; {{ end -}}  
-       <a href="{{ .RelPermalink }}">{{ .Title }}</a>  
**+       <a href="{{ .RelPermalink }}"> IW_Read {{ .Title }}</a>**  
       {{- if .Param "authorsinlist" }}  
       {{ with .Params.authors }}  
               by    
diff -bur lugo-master/layouts/partials/nav.html ../dev.geargineer/themes/lugo/layouts/partials/nav.html  
--- lugo-master/layouts/partials/nav.html       2025-02-28 12:55:01.000000000 +0100  
+++ ../dev.geargineer/themes/lugo/layouts/partials/nav.html     2026-03-15 17:26:33.000000000 +0100  
@@ -1,6 +1,10 @@  
<nav>  
    <ul>  
-       {{- $sec := .Page.Section }}{{ $file := .File.TranslationBaseName -}}  
+       {{- $sec := .Page.Section -}}  
+       {{ $file := "undefined" }}  
+       {{ with .File }}  
+           {{ $file = .TranslationBaseName }}  
+       {{ end }}  
        {{ range.Site.Menus.main.ByWeight }}{{ $base := path.Base .URL }}  
       <li><a {{ if or ( eq $sec $base ) ( eq $file $base ) ( and (eq $sec "") ( eq $file "_index") (eq $base "/") ) }}class="menuactive" {{ end }}href="{{ .URL }}"><span class=pre>{{ .Pre }}</span><span c  
lass=menuname>{{ .Name }}</span></a></li>  
        {{- end }}
```

### Fixing missing title attribute

Is the .title attribute missing, the list.html does not list the according pages. This is made visible by adding a constant prefix IW\_read to the title variable. Proper fixing needed.

### Fixing crash of TranslationsBaseName

As found in the internet (somewhere) checking .File for existence renders getting the BaseName more robust.
