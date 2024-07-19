# The Saeed Lab Webpage

Our website, http://drummondlab.org, is a [GitHub Pages](https://pages.github.com/) site built with [Jekyll](https://jekyllrb.com/) and [Bootstrap](http://getboostrap.com), originally pulled from [Trevor Bedford's site](http://bedford.io) in 2015 and heavily modified.

# How to add content and your self in the lab webpage
Because the website code is hosted on GitHub, any lab member can contribute (and this is the intention) to the site. The general pattern will be: (1) Fork the repository to your own account; (2) Clone your fork to your laptop; (3) Make changes (e.g., add a new post to News or update your bio) to your local copy; (4) Test those changes by running a local version of the website; (5) If your changes don't break the website, commit your changes to your fork's remote; (6) Open a pull request from your fork to the main repository. Once the PR is open, the website administrator will review the changes and merge them into the main website.

You'll need a working Unix-like environment and working knowledge of Git, [Markdown](https://daringfireball.net/projects/markdown/syntax), HTML, and Unix commands.

## Overview of the structure

Let's assume you're familiar with HTML pages. A site is a collection of HTML pages. For our site (and many others), there are page types, like a paper page, or a lab member page, which are the same in design but different in content. In the web-accessible site, these are indeed different pages. However, as you might hope, they are _generated_ from a single template file filled in with information from many paper- or member-specific data files. This generation is done every time the site changes; it's handled by GitHub Pages, the service we use.

The template files are weird-looking HTML files residing in the `_includes/themes/lab` folder.

## How to add content

For most common actions---adding a lab member, paper, protocol, or news item---you'll be making a new Markdown file in the proper location, naming it properly, and filling in the required fields. In almost all cases, you can (and should!) copy an existing item, change the name, and change its content, rather than trying to write a Markdown document from scratch.

For example, suppose you want to add a news item, which will appear on the front page, announcing that you have created a yeast strain capable of secreting high-quality chardonnay. Go into the `news/_posts` folder. Copy one of the existing items into a new file named with today's date (it matters!) and a brief title:

	cp 2017-12-15-allan-tenure.md 2024-01-31-wine-yeast.md

The date is used by the generator; it's inelegant and perhaps there's a way to do it differently, but that's how it is for now. Now edit the new file to make the content what you want. Just open it in your favorite editor and type away. By the time you're done, hopefully you have something like this:

	---
	layout: news
	title: "New yeast strain makes chardonnay"
	author: "X. Obsequious Trenchcoat"
	author_handle: "xot"
	image: /assets/images/news/default-news.png
	category: news
	tags: [breakthrough]
	---
	Today we are thrilled to announce a new strain of yeast that secretes beautifully oaked chardonnay. See more details in our [preprint](http://biorxiv.org/content/10.1101/0000000)!

Now add it to the repository:

	git add 2026-01-31-wine-yeast.md

And, when you're happy with it, commit and push:

	git commit -m "announcing new yeast strain"
	git push

This new announcement won't yet be public. Make a pull request that will be reviewed by the webmaster before it appears in a live version. 

The same basic process is used to add protocols, team members, etc. For usual things follow the steps below.

## Add your self as team member
1. Fork a local copy at https://github.com/pcdslab/PCDSLab.github.io
2. Change directory to \team\_posts
3. Copy one of the .md files and rename it as follows: Date_when_you_joined_lab-LastName-FirstName.md
4. Put in all the relevant information in the .md file above.
5. Put in your picture in assets/images/team/Last_name_picture.jpg (make sure that the dimension of your picture is same as Dr. Saeed - this makes it a nice grid-like structure)
6. Once you are done with this - commit your changes and push to the main branch (with appropriate comments).
7. Pull request from the forked repo for merging the changes (with appropriate comments).
8. website administrator will review and approve.


## Changing look and feel

Fonts, colors, spacing, and similar stylings are separate from the template pages. Like most sites circa 2023, we use Cascading Style Sheets (CSS).

### To-dos

See Issues on [the site](https://github.com/drummondlab/drummondlab.github.io).


## License

[MIT](http://opensource.org/licenses/MIT)
