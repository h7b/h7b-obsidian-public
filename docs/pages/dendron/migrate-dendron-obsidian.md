---
aliases: Migrate notes out of Dendron into Obsidian
createdAt: 2023-03-25T20:05:32+01:00
dg-publish: true
modifiedAt: 2023-04-01T00:45:21+02:00
title: "Migrate notes out of Dendron into Obsidian"
---
# Migrate notes out of Dendron into Obsidian

I decided to convert all notes from Dendron into Obsidian since Dendron dev team decided to switch the project into maintenance mode from 2023-02-07 [^1]

[^1]: [announcement in Dendron discord](https://discord.com/channels/717965437182410783/737323300967022732/1072563304289030164)

## In Dendron

- use [Markdown Export Pod](https://wiki.dendron.so/notes/Un0n1ql7LfvMtmA9JEi4n/) to export and convert the notes from dendron-hierarchy-dot-style filenames to standard file-folder markdown files
    - the export pod's limitations:
        - removed all data from yaml frontmatter, 
        - convert Dendron-flavored wikilink into markdown link, 
        - convert mermaid block code into html block code
    - there's also a [python script](https://forum.obsidian.md/t/any-plugin-to-import-dendron-vault-into-obsidian/47060/2) to convert only filename, and don't touch the yaml data, or convert the Dendron syntax. But I did not use
    - I have to manually edit multiple links from Dendron style into Obsidian
    - I removed the [[./image#Resize image and display|css tag to resize image to 300px supported by Dendron]], since Obsidian use a different syntax

## In Obsidian

- set up [a template for daily note](daily-note-tp.md), automatically sorted in appropriate year by configuring the core plugin "Daily notes" -> "Date format" as "YYYY/YYYY-MM-DD", following this [tutorial](https://www.reddit.com/r/ObsidianMD/comments/10ultm1/i_learned_that_you_can_automate_your_daily_notes/)
- in `Settings` -> `Editor` -> disable `Indent using tabs`
    - reason: force Obsidian to use spaces instead of tabs to indent bullet
    - also set `Tab indent size` to `4`
- `Settings` -> `Appearance` -> disable `Show inline title`
    - reason: the file's title should not be visualized repeatedly in the note's content
- `Settings` -> `Files & Links` -> enable `Use [[Wikilinks]]`
    - reason: allow Obsidian to use wikilink format
- use [Linter](https://github.com/platers/obsidian-linter) plugin to:
    - automatically add in frontmatter these keys `createdAt`, `modifiedAt`, `title`
    - applied `Format` for `createdAt`, `modifiedAt`: `YYYY-MM-DDTHH:mm:ssZ` (explain syntax: [momentjs](https://momentjscom.readthedocs.io/en/latest/moment/04-displaying/01-format/)). Reason: the date string need to be in this format, in order to be parsed by dataview plugin into [date object](https://blacksmithgu.github.io/obsidian-dataview/annotation/types-of-metadata/#date)
    - sort the frontmatter keys
    - [Yaml aliases section style](https://github.com/platers/obsidian-linter/blob/master/docs/rules.md#yaml-aliases-section-style) > choose `single string to multi-line`
    - Yaml tags section style > choose `single string to multi-line`
    - [Force YAML escape](https://github.com/platers/obsidian-linter/blob/master/docs/rules.md#force-yaml-escape) character on key `title`
    - [Format Yaml Array](https://github.com/platers/obsidian-linter/blob/master/docs/rules.md#format-yaml-array) > disable `Format yaml aliases section`
    - [YAML Title Alias](https://github.com/platers/obsidian-linter/blob/master/docs/rules.md#yaml-title-alias) > enable `Inserts the title of the file into the YAML frontmatter's aliases section`
        - Try to not use comma `,` in heading H1. Reason: with comma inside H1, the auto-added alias will be wrong, since the alias section is a Yaml array which is also separated by comma.
- use [Dataview](https://blacksmithgu.github.io/obsidian-dataview/) plugin:
    - config `Date + Time Format` as: `ccc yyyy-MMM-dd HH:mmZZ`
    - explain: dataview use [luxon format](https://github.com/moment/luxon/blob/master/docs/formatting.md)
- try to always use [kebab-case-style](https://www.freecodecamp.org/news/snake-case-vs-camel-case-vs-pascal-case-vs-kebab-case-whats-the-difference/) in the filename of notes.
    - Reason: this gives the note a clean web URLs (slug) when publishing my vault. Read [this post](https://forum.obsidian.md/t/publish-support-for-lowercase-and-kebab-case-slugs-in-urls/32463) to understand the reason
    - Since I already enable the [YAML Title Alias](https://github.com/platers/obsidian-linter/blob/master/docs/rules.md#yaml-title-alias), then I can easily [link to a note using an alias](https://help.obsidian.md/Linking+notes+and+files/Aliases) with proper space in filename, without worrying the burden of kebab-case-style filename.
- use [AidenLx's Folder Note](https://github.com/aidenlx/alx-folder-note) plugin
    - have to install [Folder Note Core](https://github.com/aidenlx/folder-note-core) as requirement
    - use the [Inside Folder, with Same Name](https://github.com/aidenlx/alx-folder-note/wiki/folder-note-pref) strategy to specify and store folder notes, as recommended by plugin's author.
- use [Completr](https://github.com/tth05/obsidian-completr) plugin
    - enable only the `YAML Front Matter support`, since I need only to auto-suggest when editing key-value pair in the frontmatter
    - [Various Complements](https://github.com/tadashi-aikawa/obsidian-various-complements-plugin) plugin with the feature [Front matter complement](https://tadashi-aikawa.github.io/docs-obsidian-various-complements-plugin/1.%20Features/Front%20matter%20complement/) can achieve the same thing
- use [GitHub Publisher](https://github.com/ObsidianPublisher/obsidian-github-publisher) plugin
    -  [[mkdocs-pub|to publish notes with mkdocs-materials]]
- use [[languagetool-obsidian|LanguageTool integration]] plugin to enable grammar and spell checking for Obsidian notes