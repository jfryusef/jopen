+++
title = "How I Made jopen?"
date = "2025-07-06T13:41:37+03:30"
#dateFormat = "2006-01-02" # This value can be configured for per-post date formatting‍
author = "yusef"
authorTwitter = "" #do not include @
tags = ["jopen", "Markdown", "Obsidian", "Git", "GitHub", "Hugo", "Website", "Software"]
description = "How I built a blog using just Markdown and Git"
showFullContent = false
readingTime = true
hideComments = false
draft = false
+++

jopen is a blog about mostly tech-related projects I do for fun. In fact, jopen itself is one of them! I wanted to take notes on the process of my projects, and there was no reason to keep them private. So, I made this blog, *To Learn In Public*.

I don't like bloated CMSs. This stack is cheap, open-source, and lets me focus on writing in a tool I already use (Obsidian). Plus, it’s all plain text — future-proof.

Here's how I made it:

---

## Tools

- [Obsidian](https://obsidian.md/) for writing posts & local Markdown management
- [GitHub](https://github.com/) for cloud-based version control + repo hosting
- [Hugo](https://gohugo.io/) (with [Terminal](https://github.com/panr/hugo-theme-terminal/) theme) as the static site generator
- [Cloudflare Pages](https://pages.cloudflare.com/) for free, automated deployment
- [Giscus](https://giscus.app/) to integrate a comment system via [GitHub Discussions](https://github.com/features/discussions)

Every push to GitHub updates the blog via Cloudflare and every comment shows up on GitHub as well.

## Setup

#### A. Buying a domain

This was the only step in which I paid for something, purchasing this .link domain for ~$10 a year. But there were cheaper (even free) options as well.

#### B. Hugo site and Terminal theme 

I changed the font to [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) in `/themes/terminal/assets/css/terminal.css`. It's a beautiful, open-source, monospace font and I liked it more than my theme's default font, ([Fira Code](https://fonts.google.com/specimen/Fira+Code)).

And here's the list of changes I made to the `/themes/terminal/config.toml` file:

```toml
[params]
centerTheme = true
showLastUpdated = true
updatedDatePrefix = "Updated on"
readMore = "Read"
missingContentMessage = "This is not the webpage you're looking for." # A reference from the movie Star Wars: Episode IV - A New Hope
minuteReadingTime = "min[s] read"
words = "word[s]"

[params.logo]
logoText = "jopen"

[menu]

[[menu.main]]
identifier = "about"
name = "About"
url = "/about"

[[menu.main]]
identifier = "tags"
name = "Tags"
url = "/tags"

[[menu.main]]
identifier = "search"
name = "Search"
url = "https://www.google.com/search?q=site%3Ajfryusef.link+QUERY"
```

#### C. Creating a Git Repository and connecting to GitHub

I initialized the local Hugo files in [Git](https://git-scm.com/) and turned on Discussions as a feature on jopen's GitHub repo (so I can use Giscus in step F).

![GitHub repository's Discussions screenshot](/images/GitHub-Discussions-ScreenShot.jpeg)

#### D. Deploying via Cloudflare Pages

Added `jfryusef.link` and `www.jfryusef.link` as two custom domains.

#### E. Setting up Obsidian

I merged the Obsidian vault root and local files of Hugo, and every once in a while, I push its content to GitHub to sync manually because I couldn't make the [Git](https://github.com/Vinzent03/obsidian-git) plugin to work properly.

Here is the list of all the core plugins that are enabled in my vault:

- Backlinks
- Bookmarks
- Command palette
- File recovery
- Files
- Graph view
- Outgoing links
- Outline
- Page preview
- Quick switcher
- Search
- Slash commands
- Tags view
- Template
- Word count
- Workspaces

And here is the list of the community plugins that I use:

- [Style Settings](https://github.com/mgmeyers/obsidian-style-settings) - to control and adjust theme, plugin, and snippet CSS variables
- [Minimal Theme Settings](https://github.com/kepano/obsidian-minimal-settings) - to change the colors, fonts and features of [Mininmal Theme](https://github.com/kepano/obsidian-minimal)
- [File Explorer Note Count](https://github.com/ozntel/file-explorer-note-count) - to see the number of notes under each folder within the file explorer
- [Settings Search](https://github.com/javalent/settings-search) - to globally search settings in Obsidian

![jopen's Obsidian vault screenshot](/images/jopen-vault-ScreenShot.png)

And here's the metadata for this post:

```
+++
title = "How I made jopen?"
date = "2025-06-20T13:41:37+03:30"
#dateFormat = "2006-01-02" # This value can be configured for per-post date formatting‍
author = "yusef"
tags = ["jopen", "Markdown", "Obsidian", "Git", "GitHub", "Hugo", "Website", "Software"]
description = "How I built a blog using just Markdown and Git"
showFullContent = false
readingTime = true
draft = true # Until the post is finished
+++
```

#### F. Enabling Giscus

Nothing special. I just enabled comments in almost every page, because why not?

---

Feel free to share your own setups if you have something similar and If you have any questions, ask them in the comment section below.