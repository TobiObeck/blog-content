# Hello World

Welcome to my first blog post! As is tradition in the world of programming and digital content creation, I am kicking things off with a mandatory "Hello, World!" article. But this isn't much of an introduction, rather this post serves the purpose to demonstrate formatting, typography and features like code highlighting or embeds. for my own convenience. So, rather check out any other article on the [blog](/blog).

You might also notice the split view language feature. It presents the content side by side in different languages while each paragraph start vertically aligned with the translation. This is an experiment that explores if this layout could be used for learning a language. It's build with the CSS subgrid and content feature.

The rest of this post will demonstrate different elements and formatting. This is a living post, work-in-progress and will be updated continuously.

## Formatting Showcase

### Links & Lists

- [external](https://google.com)
- [internal](/)
- [linking to same page headings](#gfm)

1. First
2. Second

### Code Blocks with Syntax Highlighting

Here is an `inline` piece of code and a code block:

```js
let processor = unified()
    .use(remarkParse)    // parse into markdown syntax tree
    .use(remarkRehype)  // convert to html syntax tree
    .use(highlight) // adds class for syntax highlighting code blocks
    .use(rehypeStringify)      // turn html syntax tree to html

// process function will return the generated html string.
function processFile(filename) {
    // use vfile to read the file, could use fs if you like.
    return processor.processSync(vfile.readSync(filename));
}
```

```diff
/// file: svelte.config.js
import adapter from '@sveltejs/adapter-node';

export default {
	kit: {
-		adapter: adapter()
+		adapter: adapter({ out: 'my-output-directory' })
	}
};
```

Fun fact, on Jan 1st, 1970 time was invented: 
[https://en.wikipedia.org/wiki/Unix_time](https://en.wikipedia.org/wiki/Unix_time)

![Here is the 100x100 Fig caption](/imgs/hello-world_100x100.png "This is the hover title")
![hello text](./imgs/hello-world_100x100.png "Bread")
![Beautiful flag](./imgs/even_more_beautiful_flag.png "Title")

## GFM

### Autolink literals

www.example.com, https://example.com, and contact@example.com.

## Footnote

A note[^1]

[^1]: Big note.

## Strikethrough

~one~ or ~~two~~ tildes.

## Table

| a | b  |  c |  d  |
| - | :- | -: | :-: |
| 1 | 2 | 3 | 4 |

## Tasklist

* [ ] to do
* [x] done

| Alpha    | Bravo   |
| -------- | ------- |
| Delta       | Charlie |
| 1 | 2   |
| 3 | 4   |
| 5 | 6 |
