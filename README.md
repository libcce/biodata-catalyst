# Markdown Formatting

## File Header

Each file's YAML header must contain:

```text
---
title: "NHLBI BioData Catalyst Tutorial"
description: "NHLBI BioData Catalyst Tutorial"
time: 10
objectives:
- "Demonstrate the use of data search tools."
---
```

These values are stored in the header so that our site will read them and make them accessible in site pages.

```
$ give me super-powers
```

{% hint style="info" %}
 Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}

Once you're strong enough, save the world:

```
// Ain't no code for that yet, sorry
echo 'You got to trust me on this, I saved the world'
```

Use standard Markdown syntax:

| Element | `Markdown Syntax` |
| :--- | :--- |
| Headers | `# H1 ## H2 ### H3` |
| Bold | `**bold text**` |
| Italic | `*italicized text*` |
| Blockquote | `> blockquote` |
| Ordered List | `1. First item 2. Second item 3. Third item`  |
| Unordered List | `- First item - Second item - Third item`  |
| Code | ```code``` |
| Horizontal Rule | `---` |
| Link | `[title](https://www.example.com)` |
| Image | `![alt text](image.jpg)` |

The following extended Markdown syntax is acceptable:



| Element | Markdown Syntax |
| :--- | :--- |
| Table | `| Syntax | Description | | ----------- | ----------- | | Header | Title | | Paragraph | Text |` |
| Fenced Code Block | ``````` {   "firstName": "John",   "lastName": "Smith",   "age": 25 } ``````` |
| Footnote | `Here's a sentence with a footnote. [^1]  [^1]: This is the footnote.` |
| Heading ID | `### My Great Heading {#custom-id}` |
| Definition List | `term : definition` |
| Strikethrough | `~~The world is flat.~~` |
| Task List | `- [x] Write the press release - [ ] Update the website - [ ] Contact the media` |

