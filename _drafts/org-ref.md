---
layout: post
title: "The Miracle of org-ref
categories: [references, emacs, org-mode]
tags: [references, emacs, org-mode]
comments: true
---

Writing academic papers is hard. Managing citations shouldn't be.
Since a lot of people struggle with this, I thought that I would share
how I manage references in academic papers. This is geared towards
writing papers in LaTeX and relies on emacs heavily. I use several
emacs packages to deal with references: `reftex`, `org-mode,` and
`org-ref`. 

In your emacs dotfile you'll need to set up reftex and org-ref. 

# Bib files
A bib file keeps information about all of your references in an
organized method. One of the nice things about this is that you don't
have to actually cite everything in this file. So instead of having a
separate reference list for each article you're writing, you can just
put your bib file in your dropbox and cite articles in it with
something like `\citep{key}` in your latex document. 

An entry in your bib file looks something like this: 

```
@article{lupia1994,
  author =       {Lupia, Arthur},
  title =        {Shortcuts Versus Encyclopedias: Information and
                  Voting Behavior in California Insurance Reform
                  Elections},
  journal =      {American Political Science Review},
  volume =       {88},
  number =       {01},
  pages =        {63--76},
  year =         {1994},
}
```



# Enter org-ref

## Using org-ref in latex files

Here's the packages you need to load in the preamble:

```
\usepackage{natbib}
```

Then wherever you want your reference list to print you need:

```
\bibliogrpahystyle{chicago}
\bibliography{path/to/bibfile}
```
