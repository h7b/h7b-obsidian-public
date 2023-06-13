---
createdAt: 2023-04-25T01:18:05+02:00
dg-publish: true
modifiedAt: 2023-05-02T02:53:30+02:00
title: "Automate daily notes in Obsidian"
---
# Automate daily notes in Obsidian

## Use dataview queries

ref: [ricraftis.au](https://ricraftis.au/obsidian/automating-obsidian-daily-notes-part-4-using-dataview-queries/)

Automatically record all new notes you have created today into current daily note.

```
LIST
WHERE file.cday = this.file.day
SORT file.name asc
```

Automatically record all notes that you have modified today into current daily note.

```
LIST
WHERE file.mday = this.file.day
WHERE !contains(file.path, "daily-note-folder")
SORT file.name asc
```

## Create weekly notes

### With plugin Periodic Notes and Calendar

Use [Periodic Notes](https://github.com/liamcain/obsidian-periodic-notes) plugin to create weekly note from template.

With the template as follows
```md
# {{date:YYYY-[W]ww}}

Week {{date:ww}}: {{monday:MMM DD}} – {{sunday:MMM DD}}
```
In order to parse correctly the monday as start of the week and sunday as end of the week, I need to install [Calendar](https://github.com/liamcain/obsidian-calendar-plugin) plugin and set the `Start week on` to `Monday`.

I also learn that, I can name the weekly note in date format. In this case, the plugin will insert the date of the first day of the week. [^1]

[^1]: <https://github.com/liamcain/obsidian-periodic-notes#weekly-template-tags>

## Related

- [Get start and end date of a week using Templater script](https://www.reddit.com/r/ObsidianMD/comments/11krrbq/get_start_and_end_date_of_a_week_moment_js/)
- [Get Started With Obsidian Periodic Notes and Templater](https://kevinquinn.fun/blog/get-started-with-obsidian-periodic-notes-and-templater/): create navigation bar to traverse between weekly notes, a progress bar showing how far through the week/month/year I currently am
- [Structured daily/weekly notes - in Obsidian](https://dev.to/michalbryxi/structured-dailyweekly-notes-in-obsidian-2n5h): Templater script to insert week number, transclusion of daily notes into weekly note