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

The title displayed at the top of each page comes from the
[SUMMARY.md](./SUMMARY.md) file.


Available Markdown elements for use and syntax:

| Element | `Markdown Syntax` |
| :--- | :--- |
| Headers | `# H1 ## H2 ### H3` |
| Heading ID | `### My Great Heading {#custom-id}` |
| Bold | `**bold text**` |
| Italic | `*italicized text*` |
| Strikethrough | `~~The world is flat.~~` |
| Blockquote | `> blockquote` |
| Ordered List | `1. First item 2. Second item 3. Third item`  |
| Unordered List | `- First item - Second item - Third item`  |
| Task List | `- [x] Write the press release - [ ] Update the website - [ ] Contact the media` |
| Code | `` `code` `` |
| Horizontal Rule | `---` |
| Link | `[title](https://www.example.com)` |
| Image | `![alt text](image.jpg)` |
| Fenced Code Block | ``````` {   "firstName": "John",   "lastName": "Smith",   "age": 25 } ``````` |

## Table Markdown

GitBook allows table markdown. For instance, the following Markdown:

```
| Name | Description |
| :-- |
| First | This is the first. |
| Second | This is the second. |
```

Displays:

| Name | Description |
| :-- |
| First | This is the first. |
| Second | This is the second. |


## Explicit HTML is Ignored

According to
[the relevant GitBook docs](https://docs.gitbook.com/integrations/github/limitations#html),
arbitrary HTML content in your Markdown will not be honored.

## Display Equations

GitBook supports display equations compiled with LaTeX. Encase them in
double dollar signs as you would in a LaTeX document:

```
$$
e^{\pi i} + 1 = 0
$$
```

Becomes:

$$
e^{\pi i} + 1 = 0
$$

## Downloadable Files

You can include a link to downloadable file by adding it to your repository
and using the following markup:

```
{% file src="sample-downloadable-file.txt" %}
```

This will get rendered like this:

{% file src="sample-downloadable-file.txt" %}

## Code Samples

Standard Markdown
[fenced code blocks](https://help.github.com/en/articles/creating-and-highlighting-code-blocks),
delimited in triple backticks, work just fine. They get styled like this:

```python
print('Python sample')
```

You can use a
[language identifier](https://help.github.com/en/articles/creating-and-highlighting-code-blocks#syntax-highlighting)
to tell GitBook to apply syntax highlighting for a particular language; above,
I used the word `python` immediately after the opening backticks.

But you can also use an extended syntax that lets you show example code
associated with a specific filename, and multiple tabs that the viewer can
choose between. The syntax is:

    {% code-tabs %}
    {% code-tabs-item title="myfile.py" %}
    ```python
    print('Here is a nice Python code block.')
    ```
    {% endcode-tabs-item %}
    {% code-tabs-item title="myfile.js" %}
    ```js
    console.log('Here is some JavaScript.');
    ```
    {% endcode-tabs-item %}
    {% endcode-tabs %}

This gets rendered as:

{% code-tabs %}
{% code-tabs-item title="myfile.py" %}
```python
print('Here is a nice Python code block.')
```
{% endcode-tabs-item %}
{% code-tabs-item title="myfile.js" %}
```js
console.log('Here is some JavaScript.');
```
{% endcode-tabs-item %}
{% endcode-tabs %}

We do *not* recommend using the “tabs” feature, however, since it can be
confusing if people don’t realize that there are different pieces of code
associated with the different tabs.

## Callouts

You can include callout boxes which highlight content. Sample syntax is:

```
{% hint style="info" %}
This is an informational callout.
{% endhint %}
```

Callout styles available include `info`, `success`, `warning`, and `danger`. 

Info:

{% hint style="info" %}
This is an informational callout.
{% endhint %}

Success:

{% hint style="success" %}
Good job, you did it!
{% endhint %}

Warning:

{% hint style="warning" %}
Something might go wrong.
{% endhint %}

Danger:

{% hint style="danger" %}
Danger Zone!
{% endhint %}


## Internal Links

To make an internal link, make a link beginning with `./` and pointing to
the name of a Markdown file in the repository. Paths are relative to the
current document; for instance, to link to the previous page, I can write:

```
[a link like this](./repo-structure.md)
```

(which generates [a link like this](./repo-structure.md)), rather than having
the link text be `./gitbook-spec/repo-structure.md`.

## Web API Method Styling

GitBook provides a fairly elaborate framework for document Web API methods.
The interactive entry form is documented
[here](https://docs.gitbook.com/content-editing/rich-content#api-methods).
For reference, here is *a subset* of the special tags used in
the Markdown representation of this construct:

```
{% api-method method="get" host="https://api.example.com" path="/urlpath/:param" %}
{% api-method-summary %}
method-name
{% endapi-method-summary %}

{% api-method-description %}
Method description.
{% endapi-method-description %}

{% api-method-spec %}
(A lot of additional markup goes here, but I have not documented it since
I don't think we'll be using this construct.)
{% endapi-method-spec %}
{% endapi-method %}
```

Which results in:

{% api-method method="get" host="https://api.example.com" path="/urlpath/:param" %}
{% api-method-summary %}
method-name
{% endapi-method-summary %}

{% api-method-description %}
Method description.
{% endapi-method-description %}

{% api-method-spec %}
(A lot of additional markup goes here, but I have not documented it since
I don't think we'll be using this construct.)
{% endapi-method-spec %}
{% endapi-method %}

## Explore why these aren't working

Text prior to footnote reference.[^2]
[^2]: Comment to include in footnote.

You can also write a page reference that is called out fairly aggressively
like so:

```
{% page-ref page="../index.md" %}
```

This gets rendered as:

{% page-ref page="../index.md" %}

Once again, the file path is relative to the current Markdown file’s location
in the Git repository.
