# Posting to Ida's Corner

The blog stays intentionally simple: every post is one Markdown file in `_posts/`. No CMS, JavaScript framework, or local editor is required.

## Easiest workflow

Send ChatGPT the post in plain text and say **“post this to my blog.”**

Helpful details, when you have them:

- title
- body
- tags
- an optional one-sentence description
- an optional image and alt text
- a publication date if it should not use today's date

ChatGPT can create the correctly named Markdown file, add a supplied image to the repository, and publish the change through GitHub.

## Post format

Files use `_posts/YYYY-MM-DD-short-title.md`.

```yaml
---
title: "Post title"
description: "One sentence used on the homepage and in social metadata."
tags:
  - first topic
  - second topic
image: /assets/images/example.jpg
image_alt: "Short accessible description of the image"
---
```

`description`, `tags`, `image`, and `image_alt` are optional. The post layout is applied automatically by `_config.yml`. Everything after the front matter is normal Markdown.

## Images

Reusable images live in `assets/images/`. A post can declare one `image` for the homepage card and article hero. Images inside the body can still use normal Markdown.

## Tags

Use the `tags` list in front matter. Do not add a line of `#hashtags` to article prose just to create navigation; Jekyll builds the topic index automatically.

## Publishing safety

For a normal new post, a short-lived branch and pull request is the safest default when review is useful. For a simple typo fix or when explicitly requested, a direct publish can be used. Existing prose should not be rewritten unless requested.
