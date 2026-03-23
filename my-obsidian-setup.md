---
title: My Obsidian Setup
updated: 2026-03-23T14:46:30+07:00
tags:
  - note
  - obsidian
---

I use this as a [[second-brain|Second Brain]]  and [[Digital Garden]]

Installed Plugins:

- Frontmatter Title - Show title by a frontmatter instead of a file name. Github: https://github.com/snezhig/obsidian-front-matter-title
- Frontmatter Modified Date: Update date to editing note automatically. Github: https://github.com/alangrainger/obsidian-frontmatter-modified-date
- Style Settings - CSS plugin to deco Obsidian, Use together with Supercharged Links. Github: https://github.com/mgmeyers/obsidian-style-settings
- [[supercharged-links|Obsidian Plugin: Supercharged Links]] - Add style to blacklinks. Github: https://github.com/mdelobelle/obsidian_supercharged_links


My Settings:

**Frontmatter Title**

![[Screenshot 2569-03-23 at 14.02.57.png]]

Enable All Features

**Obsidian Plugin: Supercharged Links**

![[Screenshot 2569-03-23 at 14.05.48.png]]


And paste file `links.css` in `.obsidian/snippets`

Code from: https://forum.obsidian.md/t/internal-links-that-display-note-title-property-or-any-other/69467

```css
/* In reading view, hide link content */
.markdown-reading-view .data-link-text[data-link-title] {
  font-size: 0px;
  visibility: hidden;
  font-weight: bold;
}

/* In reading view, show linked title */
.markdown-reading-view .data-link-text[data-link-title]::before {
  font-size: 16px;
  content: "🖧 " attr(data-link-title);
  visibility: visible;
}

/* The following two blocks reverses the above if the link
 * has a display or alias attribute: ``[[link-path|display-text]]``.
 * From the inspector, it seems that any link with a display text
 * also has the following attributes set: ``data-tooltip-position``
 * and ``aria-label``.
 *
 * It seems to work?
 *
 */

/* In reading view, if there is aria-label/ tool-tip show normal link text */
/* Is this robust? non-empty tooltip means display / alias is given? */
.markdown-reading-view .data-link-text[aria-label] {
  /* content: attr(data-link-title) !important; */
  /* font-size: 16px !important; */
  visibility: visible !important;
  font-size: 16px;
}

/* In reading view, if there is aria-label/ tool-tip hide title  */
/* Is this robust? non-empty tooltip means display / alias is given? */
.markdown-reading-view .data-link-text[aria-labe]::before {
  content: none;
}

```


**Frontmatter Modified Date**

![[Screenshot 2569-03-23 at 14.15.48.png]]