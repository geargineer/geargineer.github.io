---
title: Hugo compile crashes with error
draft: "true"
date: 2026-03-15T16:59:16.342Z
lastmod: 2026-03-18T10:04:53.428Z
---
see also: [obsidian\_cms](/obsidian_cms)

## Hugo compile crashes

![Pasted image 20260308190702.png](/ob/Pasted%20image%2020260308190702.png)

Image reference in hugo-syntax:

## Solution:

see: https://discourse.gohugo.io/t/error-calling-translationbasename-runtime-error-invalid-memory-address-or-nil-pointer-dereference/49836

Add some code to partial nav.html:

![Pasted image 20260308190819.png](/ob/Pasted%20image%2020260308190819.png)

**This solves the Problem**
