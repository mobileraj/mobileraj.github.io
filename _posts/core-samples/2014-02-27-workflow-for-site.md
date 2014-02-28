---
layout: post
category : learnings
tagline: "how content gets generated - the process"
tags : [git, workflow]
---
{% include JB/setup %}

* IDE is Sublime, Vim or Emacs. Preference is Sublime on my Mac; but I use Vim as well. Vim and Emacs from my Ubuntu machines
* Git for managing my workflow of versioning. 
* *todo* need to look at watcher like tools to the bag
* Chrome for browsing, testing with the awesome Devtools for debugging and styling
* Omnigraffle for diagramming manually; PlantUML and Graphviz for automatic generation of diagrams from ascii
* Ofcourse Jekyll to power the site.

##### Steps
> Come up with an idea, something to write about or show-off a recent piece of code

> Do the work in creating the asset - code/app/video etc.

> Create a new post *rake post title* and give it a title

> Open the post in editor *vim post* and slog

> Save occasionally to see how it looks. *jekyll serve*, view *localhost:4000* in Chrome; if already running *ctrl+c, jekyll serve*

> When done, see what needs to be checked in *git status -s* , *git add post.md* , *git commit -a -m "changes were made"* , *git push origin master*

> See it via Chrome on *mobileraj.github.io*