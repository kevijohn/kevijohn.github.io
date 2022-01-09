---
title: Setting up shop (part 1)
published: true
---

I suppose a fitting early post would be about how I set up this blog.  Early on, I thought about signing up for WordPress or standing up a server hosted somewhere and running my own WordPress instance.  After all, as of now I don't have any WordPress experience, either as a user or developer.  For me, its reputation preceeds it as: 1) a popular blogging platform, and 2) a security nightmare.  It may be selection bias on my part since I follow a lot of cybersecurity news, but when I read about WordPress, more often than not it involves some issue related to security, and it's never good.  I decided I'd rather spend my time creating content instead of administering my own private WordPress instance.  Of course I could pay for a managed instance, which is constantly patched and thus more secure, but free is always better, and that's what led me to [GitHub Pages](https://pages.github.com/).  

# Grab that domain

The first thing I did was buy a domain name for my blog.  It's not a requirement for GitHub Pages, but at this point I didn't yet know where I would host and wanted to stay portable.  It took a long time to decide on a name that wasn't already taken, and then decide who to register with. I ended up going with [NameSilo](https://www.namesilo.com/) for domain registration.  

# Create the repo

Next step was to create a repo for the blog.  GitHub is very specific about how you name the repo, and you can only have one Pages repo per GitHub user.  There may be other options for organizations and projects,  but it started to feel like I was going down a rabbit hole that ultimately was not a good fit for my needs.  I'm not going to spend time here going into detail of setting up GitHub Pages, [see here](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site) for GitHub's own documentation.  By default, the URL for a GitHub Pages site is http://\<github username\>.github.io.  At the end of the setup process, I was able to navigate to <https://kevijohn.github.io> and see the contents of the readme.md file in the repo (I've since built out the full blog which takes place of the readme on the page).  

It's alive! ALIVE!!!

# Point the domain to the repo

Now we're getting somewhere!  Next I needed to point the custom domain I bought to the repo I created.  This was the secret magic voodoo that I've never seen covered in tutorials.  I still don't know exactly how it would be handled if I hosted my blog on a VPS, cloud instance, or at WordPress.com.  In my case, there were changes I had to make on both the GitHub Pages side and the registrar side.  On GitHub, thankfully there were [directions already prepared for this use case](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).  Whenever those directions talk about DNS provider, in my case they meant my domain registrar.

After that, I had to go to NameSilo and follow their instructions for configuring DNS.  Thankfully they already had a template specifically for GitHub, I just needed to apply it to my domain's configuration.  Lastly, I had to wait some time for all these changes to propagate through various DNS servers.

DON'T FORGET the [custom domain verification](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages) step!

# More to come

Next I'll go over setting up the actual blog and all the fun I had doing that.