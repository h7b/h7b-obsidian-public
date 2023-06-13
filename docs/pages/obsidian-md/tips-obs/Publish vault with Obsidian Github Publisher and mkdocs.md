---
aliases: Publish vault with Obsidian Github Publisher and mkdocs
createdAt: 2023-03-16T01:43:50+01:00
dg-publish: true
modifiedAt: 2023-05-03T21:40:09+02:00
title: "Publish vault with Obsidian Github Publisher and mkdocs"
---
# Publish vault with Obsidian Github Publisher and mkdocs

In a beautiful day, I have interest to publish [[../../../unsorted/stock-trading-spreadsheet/Trading Journal to Measure Stock Trading Performance With Google Sheets|a trading journal]] using [mkdocs](https://www.mkdocs.org/). In my setup, I use the [GitHub Publisher](github-publisher.md#) plugin to send the notes written in Obsidian, into a GitHub repository, then deploy on [Netlify](https://www.netlify.com/) and [Cloudflare Pages](https://pages.cloudflare.com/).

## Steps to install and configure

### with Netlify

1. Create a new repository from [this template](https://github.com/ObsidianPublisher/publisher-template-netlify) [^1]. This new repo will be called `trade-bt-mkdocs`
2. Connect my Netlify account to the repo `trade-bt-mkdocs` and deploy via Netlify
   - Retrieve the URL of deployed site in `Domain settings` within Netlify
   - Read the [tutorial in details](https://obsidian-publisher.netlify.app/getting%20started/publishing/) to learn how to deploy
3. Since I deploy via Netlify, I have to modify the `requirements.txt` as discussed at [here](https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions/63#discussioncomment-4608415)
   - Change: `obsidiantools==0.10.0` -> `obsidiantools==0.8.1`. Reason: Netlify only support python 3.8
4. Configure in "GitHub Publisher" plugin settings
    - [Create a personal access token (classic)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) then paste it into the "GitHub Token" field in "GitHub Configuration" tab. Also change "Repo Name", "Github Username"
    - I did not choose the new `fine-grained personal access token` as instructed [^2], because it requires an expiry date within 1 year, and I don't want to set an expiry date for this token
    - In `Plugin Settings` tab,
        - change `Share Key` to `dg-publish`. Reason: I want to use the same publishing keyword with [Obsidian Digital Garden](digital-garden.md#)
        - change `Excluded Folder` to `99_template`. Reason: I don't need to publish any notes within this folder
    - In `Upload Configuration` tab,
        - set `Folder behavior` to `Obsidian Path`. I want to replicate the folder structure of Obsidian vault to the published site [^3]
        - set `Default folder` to `docs`
    - In `Content's conversion` tab,
        -  enable `Internal Links`
        - disable `[[Wikilinks]] to [MDlinks](links)`. Reason: possible error when mkdocs-material render anchor link from mdlink syntax [^8]
        - disable `Convert internal links into unpublished notes`
5. Close and reopen Obsidian to assure that the changes are executed. Because I also encounter the same error as this user's [issue](https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions/63#discussioncomment-4599564)
6. Configure the file `mkdocs.yml` in the repo `trade-bt-mkdocs`
    - change the `site_url` into the valid Netlify link from previous step
    - add the [Navigation footer](https://squidfunk.github.io/mkdocs-material/setup/setting-up-the-footer/#navigation) to include links to the previous and next page of the current page
    - change the [colors](https://squidfunk.github.io/mkdocs-material/setup/changing-the-colors/)
    - change the [fonts](https://squidfunk.github.io/mkdocs-material/setup/changing-the-fonts/)
    - change the [logo and icons](https://squidfunk.github.io/mkdocs-material/setup/changing-the-logo-and-icons/)
    - (optional) set up the [navigation tree](https://squidfunk.github.io/mkdocs-material/setup/setting-up-navigation/). I didn't do this step. Because i don't want to change manually the items in the navigation tree whenever I change the file structure
    - add a [git repository](https://squidfunk.github.io/mkdocs-material/setup/adding-a-git-repository/)
7. Enable the `Comments` section for specific page only
    - Update 20230114, according this [reply of plugin developer](https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions/70#discussioncomment-4678758), she has recently updated the template. Please follow her [updated tutorial](https://obsidian-publisher.netlify.app/advanced%20setup/customization/#comments) to learn how to enable/disable the `Comments` section for the whole website or for a specific page only
    - Read [here](https://squidfunk.github.io/mkdocs-material/reference/?h=template#setting-the-page-template) to understand why the key `template: custom.html` works
    - In this [section](https://squidfunk.github.io/mkdocs-material/customization/#extending-the-theme), the author explain how to extend the `mkdocs-material` using the `custom_dir` setting, what's the meaning of folder `overrides`, `partials`
    - (obsolete, update 20230114) in GitHub repo, path `trade-bt-mkdocs/overrides/`, duplicate the `main.html` as `page_comments.html`. After that, in the note (page) where I want to enable the comments, I will add the key `template: page_comments.html` in its frontmatter. [^4]
8. (Optional) Disable the workflow `Building Mkdocs Page` in GitHub Actions [^5], since I deploy solely via Netlify. This only helps the repo status clean. It does not affect on the success of build process.
9. Create a custom front page
    - Follow this [issue](https://github.com/squidfunk/mkdocs-material/issues/1996) and replicate a `home.html` with examples from [up42-py](https://github.com/up42/up42-py/blob/master/docs/theme_override_home/home.html), [le-ref-architecture-doc](https://github.com/binbashar/le-ref-architecture-doc/blob/master/material/overrides/home.html), [mkdocs-material](https://github.com/squidfunk/mkdocs-material/blob/master/src/.overrides/home.html)

[^1]: <https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template>

[^2]: <https://dg-docs.ole.dev/advanced/fine-grained-access-token/>

[^3]: <https://obsidian-publisher.netlify.app/obsidian/#upload-configuration>

[^4]: <https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions/70#discussioncomment-4656676>

[^5]: <https://docs.github.com/en/actions/managing-workflow-runs/disabling-and-enabling-a-workflow>

[^8]: read my [discussion](https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions/131#discussioncomment-5494065) for details

### with Cloudflare Pages

1. Create a new repository from [this template](https://github.com/ObsidianPublisher/obsidian-mkdocs-publisher-template/). This new repo will be called `trade-bt-mkdocs`
2. Connect my Cloudflare account to the repo `trade-bt-mkdocs` and deploy via [Cloudflare Pages](https://pages.cloudflare.com/)
   - Retrieve the URL of deployed site in `Domain settings` within Cloudflare
3. Since Cloudflare Pages support only up to `python 3.7` [^6], i need to modify the file `trade-bt-mkdocs/runtime.txt` from `3.8` to `3.7`. And also modify the `requirements.txt` as in configuration step with Netlify
4. From step 4 through 9, they are similar to the Netlify part.

[^6]: <https://developers.cloudflare.com/pages/framework-guides/deploy-an-mkdocs-site/>

## Customize GitHub Publisher template repo

In the [template repo for Netlify](https://github.com/ObsidianPublisher/publisher-template-netlify), the author included [many plugins](https://obsidian-publisher.netlify.app/advanced%20setup/).

### Disable plugins

Some plugins which I don't use will be disabled

In `mkdocs.yml`
- disable plugin [meta-descriptions](https://pypi.org/project/mkdocs-meta-descriptions-plugin/)
- disable plugin [git-revision-date-localized](https://github.com/timvink/mkdocs-git-revision-date-localized-plugin)
    - reason: I don't want to show the "Last update status" in the footer of published page
- disable plugin [mermaid2](https://github.com/fralau/mkdocs-mermaid2-plugin)
    - reason: Material for MkDocs integrates with [Mermaid.js](https://mermaid-js.github.io/mermaid/) natively since v8.2 [^7], we don't need to use a 3rd party plugin
- disable plugin [encryptcontent](https://github.com/unverbuggt/mkdocs-encryptcontent-plugin)
    - reason: I don't need the feature to have password protected articles and pages
- disable the [option to visualize the Graph View](https://obsidian-publisher.netlify.app/advanced%20setup/customization/#graph-view), similar to "Graph View" in Obsidian
    - reason: it doesn’t allow you to click on article/post. You can only see the graph of connected notes. It's a cosmetic feature
- [Sticky navigation tabs](https://squidfunk.github.io/mkdocs-material/setup/setting-up-navigation/#sticky-navigation-tabs)
- [Navigation sections](https://squidfunk.github.io/mkdocs-material/setup/setting-up-navigation/#navigation-sections)
- [Navigation expansion](https://squidfunk.github.io/mkdocs-material/setup/setting-up-navigation/#navigation-expansion)
- Disable [built-in tags plugin](https://squidfunk.github.io/mkdocs-material/setup/setting-up-tags/#+tags.tags_file). This plugin adds a [tags index](https://squidfunk.github.io/mkdocs-material/setup/setting-up-tags/#adding-a-tags-index) into the published website. However, the nested tags feature of Obsidian is not supported by mkdocs-material
    - I also deleted the file "./docs/tags.md" which is served as the [tags index](https://squidfunk.github.io/mkdocs-material/setup/setting-up-tags/#adding-a-tags-index). When I want to reuse this feature, I have to recreate this file

[^7]: <https://squidfunk.github.io/mkdocs-material/reference/diagrams/>

### Enable plugins

- enable the option [toc.permalink](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/#+toc.permalink)
    - reason: This option adds an anchor link containing the paragraph symbol `¶`. Which makes easier to copy the anchor link
- [Instant Loading](https://squidfunk.github.io/mkdocs-material/setup/setting-up-navigation/#instant-loading)
    - reason: this option allows Material for MkDocs to behave like a Single Page Application, ie. clicks on all internal links will be intercepted and opened without fully reloading the page
- [Anchor tracking](https://squidfunk.github.io/mkdocs-material/setup/setting-up-navigation/#anchor-tracking)
    - reason: the URL in the address bar is automatically updated with the active anchor as highlighted in the table of contents
- [Anchor following](https://squidfunk.github.io/mkdocs-material/setup/setting-up-navigation/#anchor-following)
- [Navigation tabs](https://squidfunk.github.io/mkdocs-material/setup/setting-up-navigation/#navigation-tabs)
- [Back-to-top button](https://squidfunk.github.io/mkdocs-material/setup/setting-up-navigation/#back-to-top-button)
- [Code copy button](https://squidfunk.github.io/mkdocs-material/reference/code-blocks/?h=copy+bu#code-copy-button)
- [A "view source" button can be shown next to the "edit this page" button](https://squidfunk.github.io/mkdocs-material/upgrade/#contentaction)
- [Section index pages](https://squidfunk.github.io/mkdocs-material/setup/setting-up-navigation/#section-index-pages)
    - This plugin enables the implementation of [[folder-note|Folder Note plugin]] in Obsidian
    - When publishing using [[github-publisher|GitHub Publisher plugin]], this [folder note feature](https://obsidian-publisher.netlify.app/github%20publisher/settings/upload/#folder-note) is also integrated
- enable [no-auto-h1](https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions/128#discussioncomment-5473672), which disable the automatic generation of h1 if no h1 is found. This help to solve [the problem of duplicated page's title and heading H1](https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions/128)
- enable the option to use only Unicode characters and all lower case in slugs
    - [toc.slugify](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown/#+toc.slugify): applied for "Table of Contents". Otherwise, I can also use the `Slugify anchor in markdown links` option from the [github-publisher plugin for Obsidian](https://github.com/ObsidianPublisher/obsidian-github-publisher)  to achieve the same behavior, as discussed with the plugin's author in [Discussion #131](https://github.com/ObsidianPublisher/obsidian-github-publisher/discussions/131)

### In-consideration plugins

- [custom-tags-attributes](https://pypi.org/project/mkdocs-custom-tags-attributes/). I don't need the feature [to create inline markdown attributes](https://obsidian-publisher.netlify.app/advanced%20setup/customization/#inline-markdown-attributes). But it seems to be used in companion with plugin [embed-file](https://pypi.org/project/mkdocs-embed-file-plugins/). So don't touch yet
- Read this [tutorial](https://obsidian-publisher.netlify.app/mkdocs%20template/configuration/) from GitHub Publisher plugin's author to learn some extra configuration related SEO and blog list
- Read this [tutorial](https://obsidian-publisher.netlify.app/mkdocs%20template/#upgrading) to learn how to update the GitHub Publisher template repo
- Read this [tutorial](https://obsidian-publisher.netlify.app/advanced%20setup/customization/#comments) to learn how to add a "Comments" section under each post. Though I don't recommend using this, since it makes the UI so cluttered
- Since the [built-in blog plugin](https://squidfunk.github.io/mkdocs-material/setup/setting-up-a-blog/) is currently in "Sponsors only" tier (version insiders-4.23.0), GitHub Publisher plugin implement a [special template workaround](https://obsidian-publisher.netlify.app/advanced%20setup/customization/#article-list) to display the post as a timeline of blog.
- the option to use only Unicode characters and all lower case in slugs
    - [pymdownx.tabbed.slugify](https://squidfunk.github.io/mkdocs-material/setup/extensions/python-markdown-extensions/?h=slugify#+pymdownx.tabbed.slugify): applied for "content tabs"
    - [blog.post_slugify](https://squidfunk.github.io/mkdocs-material/setup/setting-up-a-blog/?h=slugify#+blog.post_slugify): applied for "blog post titles". Not available for free user at the moment since the [built-in blog plugin](https://squidfunk.github.io/mkdocs-material/setup/setting-up-a-blog/) is currently in "Sponsors only" tier (version insiders-4.23.0)
    - [blog.categories_slugify](https://squidfunk.github.io/mkdocs-material/setup/setting-up-a-blog/?h=slugify#+blog.categories_slugify): applied for "categories in blog". Not available for free user at the moment
    - [tags.tags_slugify](https://squidfunk.github.io/mkdocs-material/setup/setting-up-tags/?h=slugify#+tags.tags_slugify): applied for generating URL-compatible slugs from tags

### Upgrade the GitHub Publisher template repo

To keep your template up to date, you should follow [this tutorial](https://obsidian-publisher.netlify.app/mkdocs%20template/#upgrading).

In my repo "h7b-public-mkdocs"
- folder "/.github/workflows", there's a [GitHub Actions](https://github.com/features/actions) named "auto_update.yml". This action will automatically update the template every 24h
- I need to register the repo token as an [encrypted secret for a repository](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository). This "secret" is named as "GH_TOKEN".

## How to write notes and then publish?

1. Write note in Obsidian
2. In the note's frontmatter, add the key `dg-publish: true`. This action mark that this specific will be sent to the `trade-bt-mkdocs` repo and then deploy via Netlify
3. <kbd>CTRL + P</kbd> to open `Command Palette` in Obsidian, search for
    - command `Github Publisher: Share active file` to send only this active note
    - or command `Github Publisher: Upload all shared note` to send all the notes with the key `dg-publish: true`

## Notes

### Working folder of a mkdocs repository

Each Markdown file inside the folder `docs` will be rendered as a page of the site. The index page is located at `docs\index.md`. Sub-folders are used as the path to a group of related posts.

If a post is named other than `index.md`, the filename will be used as the directory path of the generated page. Here is how MkDocs generates URLs for Markdown posts:

- folder `docs` becomes the root of the site `www.site.com/`
- file `docs\blog\post.md` becomes the link `www.site.com/blog/post/`
- file `docs\blog\post\index.md` also becomes the link `www.site.com/blog/post/`

## Related

- [Mkdocs Publish Obsidian](mkdocs-publish-obsidian.md#)
- [Obsidian Mkdocs Publisher : A free publish alternative](https://forum.obsidian.md/t/obsidian-mkdocs-publisher-a-free-publish-alternative/29540)
    - in this thread in Obsidian forum, the plugin owner explain her changelog
- [Deploy MkDocs with Material or Material Insiders theme to Netlify](https://www.starfallprojects.co.uk/projects/deploy-host-docs/deploy-mkdocs-material-netlify/)
- [Deploy MkDocs with Material or Material Insiders theme to Cloudflare Pages](https://www.starfallprojects.co.uk/projects/deploy-host-docs/deploy-mkdocs-material-cloudflare/)
- [Cloudflare Docs | Deploy an Mkdocs site](https://developers.cloudflare.com/pages/framework-guides/deploy-an-mkdocs-site/)
- [A Guide to Create a Personal Site using Material for MkDocs | codeinsideout](https://www.codeinsideout.com/blog/site-setup/create-site-project/)