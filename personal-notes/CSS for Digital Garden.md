---
dg-publish: true
---
> [!tip] How to modify the CSS of the Digital Garden?
> You can modify the .css of the page that Digital Garden publishes/deploys. To do it, you should modify: ==src/site/styles/custom-style.scss== of your Digital Garden repository.

##### Below is my custom-style.scss:
```css
body {
    --font-text-theme: sans-serif;
}
.markdown-preview-view {
    line-height: 1 !important;
}
/* Search button */
.search-button {
    border: 2px solid #585b70 !important;
    border-radius: 10px !important;
}
/* Inline Code */
.markdown-rendered code {
    background-color: #484b69;
    padding: 0.15em 0.25em;
    color: #cdd6f4;
    border-radius: 7px;
}
/* Code block background colour */
.markdown-rendered pre {
    border-radius: 10px !important;
    background-color: #2b2c3e !important;
    border: 1px solid #89b4fa;
}
code[class*="language-"], pre[class*="language-"] {
  background-color: #2b2c3e !important;
}

/* Callout border radius */
.callout {
  border-radius: 10px;
}

/* Font Properties for bold, italic and highlight */
/* Highlight properties */
.markdown-rendered mark, .cm-s-obsidian span.cm-formatting-highlight, .cm-s-obsidian span.cm-highlight {
  background-color: transparent !important;
  font-weight: 700 !important;
  color: #fab387 !important;
  }
  
/* bold properties */
strong, .cm-strong {
  color: #cdd6f4 !important;
  font-weight: 700 !important;
  }
  
/* italic properties */
em, .cm-em {
  color: #cdd6f4 !important;
  font-style: italic;
  }

/* Strike through properties ~~strike~~ */
s {
  text-decoration: underline !important;
  font-weight: 700 !important;
  color: #f9e2af !important;
}
```
