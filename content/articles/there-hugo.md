---
title: "There Hugo"
date: 2018-02-05T12:28:14+01:00
---

This site has now migrated from [Drupal](https://drupal.org), a content management system made in [PHP](https://php.net), to [Hugo](http://gohugo.io/), a static site generator written in [Go](https://golang.org/).

That's quite the change, eh? The reason for building the previous incarnation of this site in Drupal
is explained by my [long history](https://www.drupal.org/u/xano) of working with, on, and for this great piece of software.
As with everything, there's a right tool for the job. Over time, it became clear the site did not need to be nearly as dynamic
and powerful as a CMS like Drupal, and static site generation tools have become easy, fast, and secure alternatives.
As both the job and the available tools have changed, I started looking at static site generators, and quickly settled for Hugo,
because it's fast, supports the content architecture I was looking for, and because it would be a good starting point for writing some Go myself.
Perhaps.

Until now, building this site with Hugo has indeed been easy and fun. The [quick start instructions](https://gohugo.io/getting-started/quick-start/)
let you set up your first site within minutes. *Static site generators* generate *static sites*,
which describes a type of website that only uses *static files*.
These are files that do not need to be executed (like PHP or [Python](https://www.python.org/) files), such as HTML, CSS, JavaScript, and media files.
The advantage is that your web server does not need additional software, and because no custom files are *executed* on your server,
your pages will generally be served faster. And if no code is executed, that means no *malicious* code can be executed either.
This, in turn, makes your site more secure, and means you generally do not need to update the software you use as often, reducing maintenance time and costs.

> You know, the root of the word "static" is a Greek word. "Static" come from the Greek word "στατικός," which is mean "static," so there Hugo.
>
> \- Kostas Portokalos -

So what *is* this new job the site has? As you can see, a new [Articles](/articles) section was introduced. This is where I will
be publishing technology tutorials, demos, experiences, and highlights. The topics will differ,
depending on what keeps me busy in the field of technology, and I'm sure there will be plenty of interesting discoveries to share.
