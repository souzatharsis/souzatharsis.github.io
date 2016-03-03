---
layout: post
title: "The Miracle of org-ref"
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

There are plenty of tools around that keep track of PDFs and notes for
all the articles that we read. I've shied away from using these
because they tend to be closed source (like
[mendeley](https://www.mendeley.com/home/c/?e=238)) or have layouts
that I could never really get used to (like
[zotero](https://www.zotero.org/)). Plus, I like to do as much as
possible in emacs. 

# Enter org-ref

For a while, I would just manually add entries to a bib file. I played
around with a few different ways of doing this (JabRef, copy/pasting
the bibtex entry from Google Scholar, etc) but never really found
anything great. . But then I found `org-ref.` And ho-boy, is that
thing awesome. It can *automatically* download a properly formatted
reference and add it to your bib file. While it does that, it checks
whether you have the article downloaded already and if not, it tries
to download it for you. While it's at it, it can also serve as notes
manager, allowing you to easily switch from bib entry to notes (and
back again).[^1]


## Setup 

This is the current setup I have for org-ref in my dotemacs file. Note
that it relies on the excellent `use-package` package as well as
MELPA. You can find my full, current emacs setup on my
[github repo](https://github.com/jabranham/emacs).

```emacs-lisp
(use-package org-ref
  :ensure t
  :init
  (setq reftex-default-bibliography '("~/Dropbox/bibliography/references.bib"))
  (setq org-ref-bibliography-notes "~/Dropbox/bibliography/notes.org"
        org-ref-default-bibliography '("~/Dropbox/bibliography/references.bib")
        org-ref-pdf-directory "~/Dropbox/bibliography/bibtex-pdfs/")
  (setq helm-bibtex-bibliography "~/Dropbox/bibliography/references.bib")
  (setq helm-bibtex-library-path "~/Dropbox/bibliography/bibtex-pdfs")
  (setq helm-bibtex-notes-path "~/Dropbox/bibliography/notes.org")
  (setq org-ref-default-citation-link "citep"))
```

This informs org-ref about three things on your computer:
1. The location of your main .bib file
2. The location of your notes file[^2]
3. The location of the folder for your PDFs. 

You can change the folder structure to suit your needs. I have mine
set up inside Dropbox so that it's automatically synced across several
computers. So I have inside Dropbox:

    ~/Dropbox/bibliography
    |--- notes.org
    |--- references.bib
    |--- helm-bibtex-

## Usage 

[^1]: Once you've got a reference in your bib file, you can easily
navigate to the paper (if you have it downloaded) with a simple `M-x
org-ref-open-bibtex-pdf`. It automatically opens the file for you (in
emacs, of course). You can also go to your notes for that article with
`M-x org-ref-open-bibtex-notes`.

[^2]: You can have either one large notes file for everything or one
    file for each bib entry separately. I prefer one large file, so
    that's how mine is set up.
