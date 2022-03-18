---
title: Renaming things using Visual Studio
published: true
---

[Phil Karlton](https://www.karlton.org/karlton/) [is claimed to have said](https://www.karlton.org/2017/12/naming-things-hard/), "There are only two hard things in Computer Science: cache invalidation and naming things."  So then what about renaming things: should it be just as hard (i.e. "naming again"), or easier (hindsight being 20/20 and all that)?  After all, it's not as if names of things are written in stone once they are typed into an editor.  They're just characters on the screen that happen to mean something (certainly to the computer, hopefully to you, and most hopefully those two things are in alignment).  But when you start building out a codebase peppered all about with those names, changing direction can start to get hairy.  But wait kevijohn, you might say, that's what find-and-replace is for, every editor worth its salt can do that, and many command line utilities exist for that purpose.  Just use those!  To that I would say, yes, find-and-replace can rename things, but the results might not be as you expect, and in fact, might cause more confusion and more work to resolve.

For example, let's say we're working in Microsoft Visual Studio, and we've got a solution with multiple projects.  And let's say those projects were generated from a template, where the names of things were prefixed with "Rename_" because you're supposed to rename those things to be more specific to what the project is for.  Maybe it's a web app, and each project has a folder "Rename_Controllers", and there are template-generated controller classes named like "Rename_LoadDataController" and endpoints like "Rename_LoadDataAction".  Not only that, but the objects also have "Rename_" in the names.  Did I mention the filenames also have "Rename_" prepended as well?  No?  Well they do. 

Now, doing a global find-and-replace on the entire solution will at best touch every string in every file, which may or may not be what you want if the "replace" part of the operation changes "Rename_" to anything else other than an empty string.  But the whole point of adding "Rename_" was to get a dev to update the names to be specific to the product and/or function!  Also, the strings in the file would be updated but the names of the files themselves would not, so that will be a separate operation done outside of Visual Studio.

Okay kevijohn, you say, I get it, renaming things en masse is hard once you're aways down a given code path but then re-consider your life choices and want to pivot your nomenclature.  

It turns out Visual Studio has a handy rename function built in!  In an open file, right click on any identifier and click "Rename..." in the context menu:

![vs-rename-context](/img/renaming-things/vs-rename-context.png)

This will open up a super handy mini-menu / dialog / whatchamacallit box in the upper right corner of the document tab:

![vs-rename-options](/img/renaming-things/vs-rename-options.png)

Not only will it count in how many files and how many times the name is referenced, but also offer to rename the file itself (if you happen to be renaming a class name in a class file of the same name).  This will work for method and variable names too.

I DID NOT KNOW THIS WAS HERE AND I'VE BEEN USING VISUAL STUDIO FOR 16 YEARS!!!  I cannot understate how forehead-slappingly stupid I felt when I found this was under my nose for at least the past 6 years.  Was it there in 2008?  2010?  I supposed I could spin up a VM with those oldies just to see, but I'd rather leave well enough alone.

So there you go: I was today years old when I learned VS would help me rename things in a way that find-and-replace can't.