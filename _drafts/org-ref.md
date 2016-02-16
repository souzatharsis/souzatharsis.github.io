---
layout: post
title: "The Miracle of org-ref
categories: [references, emacs, org-mode]
tags: [references, emacs, org-mode]
comments: true
---

I've already written one post about
[reference management using a bib file](/blog/2015/09/reference-management.html)
and another about
[harnessing the power of emacs to make references in latex](/blog/2015/09/emacs-for-social-science.html).
What could be left? For most people, probably nothing. Those two posts
are enough to have a pretty decent setup. So what more could we want? 

# Enter org-ref

For a while, I thought that was good enough. But then I found
`org-ref.` And ho-boy, is that thing awesome. It can *automatically*
download a properly formatted reference and add it to your bib file.
While it does that, it checks whether you have the article downloaded
already and if not, it tries to download it for you. 

Once you've got a reference in your bib file, you can easily navigate
to the paper (if you have it downloaded) with a simple `M-X
org-ref-open-bibtex-pdf`. It automatically opens the file for you (in
emacs, of course). You can also go to your notes for that article with
`M-x org-ref-open-bibtex-notes`. 

## Setup 

## Usage 
