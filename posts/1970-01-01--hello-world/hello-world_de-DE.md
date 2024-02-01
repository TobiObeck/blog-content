# Hallo Welt

Willkommen zu meinem ersten Blogeintrag! Wie in der Welt der Programmierung und der Erstellung digitaler Inhalte üblich, beginne ich mit einem obligatorischen "Hello, World!"-Artikel. Aber das ist keine wirkliche Einführung, sondern dieser Beitrag dient eher dazu, Formatierung, Typografie und Funktionen wie Code-Hervorhebung oder Einbettungen zu demonstrieren. zu meiner eigenen Bequemlichkeit. Schauen dir also lieber einen anderen Artikel auf dem [blog](/blog) an.

Vielleicht fällt dir auch die Funktion der geteilten Ansicht auf. Sie zeigt den Inhalt nebeneinander in verschiedenen Sprachen an, wobei jeder Absatz vertikal mit der Übersetzung beginnt. Dies ist ein Experiment, mit dem untersucht wird, ob dieses Layout zum Erlernen einer Sprache verwendet werden kann. Es wurde mit dem CSS-Untergitter und der Inhaltsfunktion erstellt.

Im weiteren Verlauf dieses Beitrags werden verschiedene Elemente und Formatierungen vorgestellt. Dies ist ein lebendiger Beitrag, der laufend aktualisiert wird.

## Formatierung Showcase

### Links & Listen

- [extern](https://google.com)
- [intern](/)
- [linking to same page headings](#gfm)

1. Erste
2. Zweite

### Code-Blöcke mit Syntax-Hervorhebung

Hier ist ein "Inline"-Stück Code und ein Code-Block:

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

Erheiternde Randbemerkung, am 01.01.1970 wurde die Zeit erfunden:

[https://de.wikipedia.org/wiki/Unixzeit](https://de.wikipedia.org/wiki/Unixzeit)

![Wunderschöne Flagge](./imgs/beautiful_flag.png "Title")

## GFM

### Autolink literals

www.example.com, https://example.com, and contact@example.com.

## Fußnote

Eine Notiz[^1]

[^1]: Große Notiz.

## Durchgestrichen

~eins~ oder ~~zwei~~ Tilden.

## Eine Tabelle mit verschiedenen Textausrichtungen

| Normal | Links  | Rechts | Zentriert |
| - | :- | -: | :-: |
| 1 | 2 | 3 | 4 |

## Aufgabenliste

* [ ] aufgabe
* [x] erledigt

## Ein größere Tabelle mit Harry-Potter-Figuren

Figuren mit einem anderen Namen im Englischen sind **fett** markiert.

| Gryffindor             | Hufflepuff            | Ravenclaw            | Slytherin            | **Lehrer**                | Muggel               |
|------------------------|-----------------------|----------------------|----------------------|-----------------------|----------------------|
| Harry Potter           | Cedric Diggory        | Luna Lovegood        | Draco Malfoy         | Albus Dumbledore      | Vernon Dursley       |
| **Hermine** Granger        | Nymphadora Tonks      | Cho Chang            | Severus Snape        | Minerva McGonagall    | Petunia Dursley      |
| Ron Weasley            | Pomona Sprout         | Filius Flitwick      | Pansy Parkinson      | Severus Snape         | Dudley Dursley       |
| Neville Longbottom     | Newt Scamander        | Gilderoy Lockhart    | Blaise Zabini        | Rubeus Hagrid         | Marge Dursley        |
| Ginny Weasley          | Ernie Macmillan       | Sybill Trelawney     | Horace Slughorn      | Dolores Umbridge      | **Herr** Granger         |
| Sirius Black           | Hannah Abbott         | Marietta Edgecombe   | Regulus Black        | Remus Lupin           | **Frau** Granger         |
| James Potter           | Justin Finch-Fletchley| Michael Corner       | Tom Riddle           | Gilderoy Lockhart     | Mrs. Figg            |
| Lily Potter            |                       |                      | Bellatrix Lestrange  | Horace Slughorn       | Kathrin Fricke                     |
