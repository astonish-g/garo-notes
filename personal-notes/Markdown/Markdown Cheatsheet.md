---
dg-publish: true
---
### How to make text bold and italic

- To create a **bold** text you should put your words in `**`. For example:

	`example of a **bold text**`
	which will result in:
	example of a **bold text**

- To create _italic_ test you should put your words in `*`. For example:

	`example of an *italic text*`
	which will result in:
	example of an _italic text_

- To create a ~~strikethrough~~ text, you should put your words between `~~`. For example:

	`example of a ~~strikethrough text~~`
	which will result in:
	example of a ~~strikethrough text~~

- To create **bold and _nested_** _italic_ you should put the words between `**_`. For example:

	`example of a **bold and _nested_ italic text**`
	which will result in:
	example of a **bold and _nested italic_ text**
	This technique is useful if you want to make text **_bold and italic_** inside a **bold** sentence.

- To create the whole text both **_bold and italic_** but your words inside of `***`. For example:

	`***This whole text will be bold and italic***`
	which will result in:
	**_This whole text will be bold and italic_**
### Creating a block quote text

You should use the `>` character before your text and hit space. This will create a block quote till you hit `return`. For example:

`> This text will be a block quote.`

and this will result in this:

> This text will be a block quote. 
### Quoting code
#### Inline code

To call out code or a command with a sentence, use single backticks <`>. The text **within** the backticks **will NOT** be formatted. For example:

```bash
`This is an example of an inline code` that I added to a sentence.
```

And this will be the output of it:

`This is an example of an inline code` that I added to a sentence.
#### Code block

To add a code block, it is like above but you should put your text between three backticks <```>. For example:

```bash
git status
git add
git commit
```

Above is the result of a code block.
### Adding links

To add a link in markdown, you should place the _alt text_ between `[]` brackets followed by the link that is placed between paranthesis `()`. For example:

```bash
Do not forget to visit [GitHub Homepage](https://github.com)
```

This will result in this sentence:

Do not forget to visit [Github Homepage](https://github.com)
### Adding Links to the sections of the same .md file

It works exactly the same way as above. You can put links inside your .md file that brings the reader to the different sections of the same document. It works by linking to the headings. In GitHub, next to the headings that you have created, you will see link button when you hover your mouse on it. Copy link from that button and then put that link inside the paranthesis of your link and when the user clicks on it, it will bring the user to the linked header. The quicklinks above are created with this method.
### Adding images

Images are created exactly the same way as the links but you should add `!` before the brackets `[]` and inside the paranthesis, instead of putting a link to a page, you put the link to the image. You can either put relative link, or the full web link.

In your GitHub repositories, it is advised to put the Github link to the image instead of the relative link, this way, when the .md file is opened locally with a software, the image will be rendered perfectly.

In case that you still want to add the relative link, this is the way to do. Let's say that in your Github repository looks like this:

```bash
images/blender
blender.md
github.md
```

And let's say that you are editing blender.md to put the image in it, and your image is called `example.jpg` and it is inside the `/images/blender/` folder relative to the directory of your file. You can link your image this way:

`![blender example](images/blender/example.jpg)`

This will use the relative link for the image. If you want to put the Github link instead, in this case, instead of using the relative link above, you put the github's http link to the image.
### Creating lists
#### Unordered list

You should use `-`, `*`, `+` to create an unordered list. Here's an example:

```bash
- Example 1
- Example 2
- Example 3
```

This will result in:

- Example 1
- Example 2
- Example 3

  #### Ordered list

To create ordered lists, you have to put `1.` before your lines. Here's an example:

```bash
1. Example 1
1. Example 2
1. Example 3
```

Which will result in:

1. Example 1
1. Example 2
1. Example 3
#### Nested list

To create a nested list, after creating the parent list item, bring the list marker character `-` or `*` under the first character of the parent list file and create it that way. Here's an example:

```bash
- Parent list item
- First nested list item
- Second nested list item
```

This will result like this:

- Parent list item
	- First nested list item
		- Second nested list item

  You can create multiple levels of nested list items, mix-match list style (ordered or unordered) or use them to nest links as well.
### Task Lists

To create a task list, preface list items with a hyphen `-` and space followed by brackets `[ ]`. Here's an example:

```bash
- [x] task 1
- [ ] task 2
- [ ] task 3
```

This will result in:

- [x] task 1
- [ ] task 2
- [ ] task 3

If a task list item description begins with a parenthesis, you'll need to escape it with `\`. For example:

```bash
- [ ] \(Optional) Open a followup issue
```

which will result in:

- [ ] \(Optional) Open a followup issue
### Creating a new paragraph

To create a new paragraph or jump a line, you should leave a blank line between the written lines.
### Alerts

Alerts are nice ways of adding different notes to your markdown files. Here I will show it with an example for you to understand it faster:

```bash

> [!NOTE]

> Useful information that users should know, even when skimming content.

  

> [!TIP]

> Helpful advice for doing things better or more easily.

  

> [!IMPORTANT]

> Key information users need to know to achieve their goal.

  

> [!WARNING]

> Urgent info that needs immediate user attention to avoid problems.

  

> [!CAUTION]

> Advises about risks or negative outcomes of certain actions.

```

And this will result in this:

> [!NOTE]
 Useful information that users should know, even when skimming content.

> [!TIP]
Helpful advice for doing things better or more easily.

> [!IMPORTANT]
Key information users need to know to achieve their goal.  

> [!WARNING]
Urgent info that needs immediate user attention to avoid problems.

> [!CAUTION]
Advises about risks or negative outcomes of certain actions.
