---
date: 2020-11-05
title: "Towards Notes Managing"
categories: ["emacs"]
tags: ["tool", "note", "emacs"]
draft: true
---

I published [another website](https://study.impl.dev) for my public notes.
As I take more and more notes,
I want a place to review these notes easily and memorize them.
I previously tried Evernote, Hackmd.io, Notion,
Obsidian, and some others I don't remember.

Since I use Emacs for typing and browser to viewing,
I don't want a third window that distracts me.
So I started to try different Emacs plugins.
I want an easy-managing workflow of my knowledge base 
and free access to read from anywhere.

## Org-roam

[Org-roam](https://www.orgroam.com/)
is built on [org-mode](https://orgmode.org/)
with the [Roam](https://roamresearch.com/) philosophy of
building your second brain and encouraging creative writing.
[A guy's org-roam practice](https://www.alexkehayias.com/essays/zettelkasten-setup/)
is a nice post, and here is his
[Emacs config](https://github.com/alexkehayias/emacs.d/blob/60edaa6cd5cc4876b489fc8f2b57d2ac4726645b/init.el#L774).

The "Roam" connects all the dots, including thought pieces,
references, previous notes, and more.
It might be useful for academic writing, which needs a lot of 
references and break down opinions.
However, I only used it for about a week and switched back to 
just org-mode.
I am more comfortable managing files on myself 
but not letting the program create new files without thinking.

## Ox-hugo

I finally built another site [Study](https://study.impl.dev) 
and put my notes on it.
Unlike my blog site [impl.dev](https://impl.dev),
it uses [ox-hugo](https://ox-hugo.scripter.co/) to convert 
content from .org files to .md files.
More over, it allows you managing just one single .org file
for multiple .md files. A powerful feature.
With these .md files, Hugo generates .html pages for you.

Although, Org-mode can also publish to .html directly,
but I don't want to deal with CSS or any themes.
Hugo's massive themes make things much easier.


## Notes Managing

All in all, there is not a tool that fits all.
Tools themselves don't solve problems for human beings. 
They are not supposed to automatically do everything for us.

Our knowledge base is deliberately built by ourselves but not tools.
It presents how we organize files, folders, 
and the entire database-like content.
We can't expect to make a well-organized wiki site 
without clearly thinking of our management style.
Other than that,
tools can help with accelerating our workflows to achieve efficiency.

There are many posts about how to manage notes.
I am still learning,
and I put some of my reading notes [here](https://study.impl.dev/writing/notes-managing/).
