---
dg-publish: true
---
>[!tip]
>This snippet below hides the top bar. Coupled with the ==Snippet Commands== plug-in, you can add a hotkey to toggle it on and off.

- Create a new .css file called **hide-top-bar.css** in *.obsidian/snippets/* and put this .css code in it.

```css
.view-header {
  display: none !important;
}
```