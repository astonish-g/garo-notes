---
dg-publish: true
---
>[!tip] Below are the snippets that I am using right now:
>- Hides minimize/maximize and close buttons.
>- Changes code and code block backgrounds and borders.
>- Changes sidebar toggle button background.
>- Changes file explorer background color.
>- Changes the tab bar and top bar background color.
>- Hides left bar.
>- Justifies text to on both sides.
>- Disables text wrapping on code blocks.
>- Changes font properties for bold, italic and highlight.

```css
/* Hide title bar minimize, maximize and close buttons*/
.mod-linux .titlebar-button-container, .mod-windows .titlebar-button-container {
  display: none;
}

/* Hide bottom status bar */
/* .status-bar {
  display: none !important;
}*/

/* Code Block background colour and border */
.markdown-rendered pre {
  border-radius: 10px !important;
  background-color: #2b2c3e !important;
  border: 1px solid #89b4fa;
}

/* Code background colour, font colour, border radius and padding*/
.markdown-rendered code {
  background-color: #484b69;
  padding: 0.15em 0.25em;
  color: #cdd6f4;
  border-radius: 7px;
}

/* Sidebar Toggle button background */
.sidebar-toggle-button {
  background: #1e1e2e !important;
}

/* File explorer background colour */
.workspace-tabs .workspace-leaf {
  background: #1e1e2e !important;
}

/* Tab bar and top bar background colour */
.workspace-tab-header-container {
  background-color: #1e1e2e;
}

/* Left bar hidden - press alt+b to reveal it */
body > div.app-container > div.horizontal-main-container > div > div.workspace-ribbon.side-dock-ribbon.mod-left.is-collapsed {
  display: none;
}

/*Text justify */
/* reading mode */
.markdown-preview-view p {
	text-align: justify;
	text-justify: inter-word;	
}

/* Text Justify */
/* source view and live preview */
.markdown-source-view.mod-cm6 .cm-line {
	text-align: justify;
	text-justify: inter-word;	
}

/* Center Mermaid Content */
.mermaid {
  display: flex !important;
  justify-content: center;
}

/* Disable wrapping on code blocks in preview mode */
.markdown-rendered :not(.print) code,
body :not(.print) code {
  word-break: normal;
  word-wrap: break-word;
  white-space: pre;
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
```