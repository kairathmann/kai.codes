---
title: Moving from Simplenote to Notational FZF
hn: 21912293
---
Having recently [chosen Vim](choosing-vim) as my new text editor, I needed to re-evaluate my note-taking system. Up to that point, I had been using [Simplenote](https://simplenote.com/). Simplenote is a plaintext note-taking system that uses the first line of every note as the title – simple. It supports full-text search and tagging. Available as an app on desktop and mobile, Simplenote stores notes in its own cloud.

There is a Vim plugin called [simplenote.vim](https://github.com/simplenote-vim/simplenote.vim) that talks to the Simplenote API, but I couldn't get it to work at the time. Therefore, I needed a system that stored notes as plaintext files on the filesystem for Vim to access.

Simplenote exported my notes well, with the title – that first line of every note – becoming the filename, plus `.txt`. I bulk-renamed these to [`.md`](https://en.wikipedia.org/wiki/Markdown) with

```bash
rename 's/\.txt/\.md/' *
```

Some of my notes contained [carriage returns](https://en.wikipedia.org/wiki/Carriage_return) that showed up in Vim as `^M`. I got rid of these with

```bash
sed -i '' 's/^M//g' *
```

Note that you must type `^M` using Ctrl-v, Ctrl-m on the command-line. If you were to paste this character sequence instead, the command-line would treat it literally as "caret followed by M".

---

Years ago, I had heard podcasters in the Apple community talk about a note-taking app called [Notational Velocity](http://notational.net/) and a fork of it called [nvALT](https://brettterpstra.com/projects/nvalt/). Revisiting these, I liked the core functionality but needed it inside Vim. My wish was granted by [Notational FZF](https://github.com/alok/notational-fzf-vim). Notational FZF is a Vim plugin that lets you do full-text search on all your notes and either open a match or create a new note with your query as the title.

I have used Notational FZF for a few weeks now and really enjoy it. I have configured it to use a single notes folder, `~/notes`, whose contents started out with my Simplenote export. When I'm in Vim, I enter `:NV` to invoke the full-text search on my notes folder. The results get updated with every character I type. I navigate through the results with Ctrl-p and Ctrl-n, which are analogous to navigating through Vim's native `/` search results with p and n. Enter opens the current result, whereas Ctrl-x creates a new note with the search term plus `.md` as filename.

Notational FZF only covers searching for and creating notes. To delete the current note, I learned the Vim command `:call delete(@%)`. To rename the current note, I use the Vim plugin [rename.vim](https://github.com/danro/rename.vim) and its command `:Rename`.

In an upcoming post, I will describe how I replaced Simplenote on my iPhone.
