---
title: Choosing 1Writer
---
In a previous post, I described how I [moved from Simplenote to Notational FZF](moving-from-simplenote-to-notational-fzf) as my desktop note-taking system. With Simplenote extending to mobile as well, this post describes how I replaced Simplenote on my iPhone.

I had two must-have requirements:

* cloud sync
* full-text search

I didn't care for using Vim, [my desktop text editor](choosing-vim), on my iPhone. (There's iVim for that.)

Brett Terpstra maintains a [massive overview of iOS text editors](https://brettterpstra.com/ios-text-editors/). I used this to identify and narrow down my choices before trying them out. The winner is 1Writer.

With 1Writer, I can create a new note with one tap. I don't have to enter a filename and can immediately start writing. 1Writer names the file by its creation date, using the [correct date format](https://xkcd.com/1179/), plus time of day.

You set up a default folder for 1Writer to use, normally one from a cloud provider. I chose to sync my notes via iCloud. This required me to move my notes on the desktop into 1Writer's iCloud documents folder. The location of this folder is a bit convoluted. That's why I created a symbolic link from `~/notes` to that folder:

```bash
ln -s "~/Library/Mobile Documents/9CR7T2DMDG~com~ngocluu~onewriter/Documents" ~/notes
```

Full-text search in 1Writer works like a charm. It seamlessly incorporates edits from the desktop.
